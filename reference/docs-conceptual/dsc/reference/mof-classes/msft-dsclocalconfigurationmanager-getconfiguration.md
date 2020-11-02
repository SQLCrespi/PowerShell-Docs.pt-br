---
ms.date: 07/17/2020
ms.topic: reference
title: Método GetConfiguration
description: Método GetConfiguration
ms.openlocfilehash: a49f810bd227142c8c3ae4de45f69450400e4e8c
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650886"
---
# <a name="getconfiguration-method"></a><span data-ttu-id="1ea03-103">Método GetConfiguration</span><span class="sxs-lookup"><span data-stu-id="1ea03-103">GetConfiguration method</span></span>

<span data-ttu-id="1ea03-104">Envia o documento de configuração para o nó gerenciado e usa o método **Get** do Agente de Configuração para aplicar a configuração.</span><span class="sxs-lookup"><span data-stu-id="1ea03-104">Sends the configuration document to the managed node and uses the **Get** method of the Configuration Agent to apply the configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="1ea03-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1ea03-105">Syntax</span></span>

```mof
uint32 GetConfiguration(
  [in]  uint8            configurationData[],
  [out] OMI_BaseResource configurations[]
);
```

## <a name="parameters"></a><span data-ttu-id="1ea03-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="1ea03-106">Parameters</span></span>

<span data-ttu-id="1ea03-107">**configurationData** \[in\] Especifica os dados de configuração para envio.</span><span class="sxs-lookup"><span data-stu-id="1ea03-107">**configurationData** \[in\] Specifies the configuration data to send.</span></span>

<span data-ttu-id="1ea03-108">**configurations** \[out\] No retorno, contém uma instância inserida das configurações.</span><span class="sxs-lookup"><span data-stu-id="1ea03-108">**configurations** \[out\] On return, contains an embedded instance of the configurations.</span></span>

## <a name="return-value"></a><span data-ttu-id="1ea03-109">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="1ea03-109">Return value</span></span>

<span data-ttu-id="1ea03-110">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="1ea03-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="1ea03-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="1ea03-111">Remarks</span></span>

<span data-ttu-id="1ea03-112">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="1ea03-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="1ea03-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1ea03-113">Requirements</span></span>

<span data-ttu-id="1ea03-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="1ea03-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="1ea03-115">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="1ea03-115">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="1ea03-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="1ea03-116">See also</span></span>

[<span data-ttu-id="1ea03-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="1ea03-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
