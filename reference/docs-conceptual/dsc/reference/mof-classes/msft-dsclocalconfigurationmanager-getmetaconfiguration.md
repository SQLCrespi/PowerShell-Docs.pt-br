---
ms.date: 07/17/2020
keywords: DSC,powershell,configuração,instalação
title: Método GetMetaConfiguration
ms.openlocfilehash: 5111cb3b15e0fba0bf71b412580efdd3cd95b2dc
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463968"
---
# <a name="getmetaconfiguration-method"></a><span data-ttu-id="80b7e-103">Método GetMetaConfiguration</span><span class="sxs-lookup"><span data-stu-id="80b7e-103">GetMetaConfiguration method</span></span>

<span data-ttu-id="80b7e-104">Obtém as configurações do Gerenciador de Configurações Local usadas para controlar o Agente de Configuração.</span><span class="sxs-lookup"><span data-stu-id="80b7e-104">Gets the local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

## <a name="syntax"></a><span data-ttu-id="80b7e-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="80b7e-105">Syntax</span></span>

```mof
uint32 GetMetaConfiguration(
  [out] MSFT_DSCMetaConfiguration MetaConfiguration
);
```

## <a name="parameters"></a><span data-ttu-id="80b7e-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="80b7e-106">Parameters</span></span>

<span data-ttu-id="80b7e-107">**MetaConfiguration** \[out\] No retorno, contém uma instância inserida da classe **MSFT_DSCMetaConfiguration** que define as configurações.</span><span class="sxs-lookup"><span data-stu-id="80b7e-107">**MetaConfiguration** \[out\] On return, contains an embedded instance of the **MSFT_DSCMetaConfiguration** class that defines the settings.</span></span>

## <a name="return-value"></a><span data-ttu-id="80b7e-108">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="80b7e-108">Return value</span></span>

<span data-ttu-id="80b7e-109">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="80b7e-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="80b7e-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="80b7e-110">Remarks</span></span>

<span data-ttu-id="80b7e-111">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="80b7e-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="80b7e-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="80b7e-112">Requirements</span></span>

<span data-ttu-id="80b7e-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="80b7e-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="80b7e-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="80b7e-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="80b7e-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="80b7e-115">See also</span></span>

[<span data-ttu-id="80b7e-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="80b7e-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
