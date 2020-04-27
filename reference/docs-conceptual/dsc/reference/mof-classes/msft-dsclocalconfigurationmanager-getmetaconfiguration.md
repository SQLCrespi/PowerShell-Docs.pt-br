---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Método GetMetaConfiguration
ms.openlocfilehash: bd280cb8ebd7b0522e4e01cbd24bd9bdcfddf4c2
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "71953403"
---
# <a name="getmetaconfiguration-method"></a><span data-ttu-id="3f1f3-103">Método GetMetaConfiguration</span><span class="sxs-lookup"><span data-stu-id="3f1f3-103">GetMetaConfiguration method</span></span>

<span data-ttu-id="3f1f3-104">Obtém as configurações do Gerenciador de Configurações Local usadas para controlar o Agente de Configuração.</span><span class="sxs-lookup"><span data-stu-id="3f1f3-104">Gets the local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

## <a name="syntax"></a><span data-ttu-id="3f1f3-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3f1f3-105">Syntax</span></span>

```mof
uint32 GetMetaConfiguration(
  [out] MSFT_DSCMetaConfiguration MetaConfiguration
);
```

## <a name="parameters"></a><span data-ttu-id="3f1f3-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="3f1f3-106">Parameters</span></span>

<span data-ttu-id="3f1f3-107">*MetaConfiguration* \[out\] No retorno, contém uma instância inserida da classe **MSFT_DSCMetaConfiguration** que define as configurações.</span><span class="sxs-lookup"><span data-stu-id="3f1f3-107">*MetaConfiguration* \[out\] On return, contains an embedded instance of the **MSFT_DSCMetaConfiguration** class that defines the settings.</span></span>

## <a name="return-value"></a><span data-ttu-id="3f1f3-108">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="3f1f3-108">Return value</span></span>

<span data-ttu-id="3f1f3-109">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="3f1f3-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="3f1f3-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="3f1f3-110">Remarks</span></span>

<span data-ttu-id="3f1f3-111">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="3f1f3-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="3f1f3-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3f1f3-112">Requirements</span></span>

<span data-ttu-id="3f1f3-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="3f1f3-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="3f1f3-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="3f1f3-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="3f1f3-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="3f1f3-115">See also</span></span>

[<span data-ttu-id="3f1f3-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="3f1f3-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
