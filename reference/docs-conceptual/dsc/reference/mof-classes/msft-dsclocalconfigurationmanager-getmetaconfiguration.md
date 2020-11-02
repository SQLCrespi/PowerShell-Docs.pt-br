---
ms.date: 07/17/2020
ms.topic: reference
title: Método GetMetaConfiguration
description: Método GetMetaConfiguration
ms.openlocfilehash: deca6b8ec342a34543bbe0e1fabbc2a740a88feb
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644732"
---
# <a name="getmetaconfiguration-method"></a><span data-ttu-id="4806e-103">Método GetMetaConfiguration</span><span class="sxs-lookup"><span data-stu-id="4806e-103">GetMetaConfiguration method</span></span>

<span data-ttu-id="4806e-104">Obtém as configurações do Gerenciador de Configurações Local usadas para controlar o Agente de Configuração.</span><span class="sxs-lookup"><span data-stu-id="4806e-104">Gets the local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

## <a name="syntax"></a><span data-ttu-id="4806e-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4806e-105">Syntax</span></span>

```mof
uint32 GetMetaConfiguration(
  [out] MSFT_DSCMetaConfiguration MetaConfiguration
);
```

## <a name="parameters"></a><span data-ttu-id="4806e-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="4806e-106">Parameters</span></span>

<span data-ttu-id="4806e-107">**MetaConfiguration** \[out\] No retorno, contém uma instância inserida da classe **MSFT_DSCMetaConfiguration** que define as configurações.</span><span class="sxs-lookup"><span data-stu-id="4806e-107">**MetaConfiguration** \[out\] On return, contains an embedded instance of the **MSFT_DSCMetaConfiguration** class that defines the settings.</span></span>

## <a name="return-value"></a><span data-ttu-id="4806e-108">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="4806e-108">Return value</span></span>

<span data-ttu-id="4806e-109">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="4806e-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="4806e-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="4806e-110">Remarks</span></span>

<span data-ttu-id="4806e-111">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="4806e-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="4806e-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4806e-112">Requirements</span></span>

<span data-ttu-id="4806e-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="4806e-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="4806e-114">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="4806e-114">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="4806e-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="4806e-115">See also</span></span>

[<span data-ttu-id="4806e-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="4806e-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
