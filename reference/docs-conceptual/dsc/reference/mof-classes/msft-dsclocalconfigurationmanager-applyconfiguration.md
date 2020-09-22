---
ms.date: 07/14/2020
keywords: DSC,powershell,configuração,instalação
title: Método ApplyConfiguration
ms.openlocfilehash: bec74ccd6f75448484adfd26bf8a4af4e224eb3f
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463832"
---
# <a name="applyconfiguration-method"></a><span data-ttu-id="9399a-103">Método ApplyConfiguration</span><span class="sxs-lookup"><span data-stu-id="9399a-103">ApplyConfiguration method</span></span>

<span data-ttu-id="9399a-104">Usa o Agente de Configuração para aplicar a configuração pendente.</span><span class="sxs-lookup"><span data-stu-id="9399a-104">Uses the Configuration Agent to apply the configuration that is pending.</span></span>

<span data-ttu-id="9399a-105">Se não houver nenhuma configuração pendente, esse método reaplicará a configuração atual.</span><span class="sxs-lookup"><span data-stu-id="9399a-105">If there is no configuration pending, this method reapplies the current configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="9399a-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9399a-106">Syntax</span></span>

```mof
uint32 ApplyConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="9399a-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="9399a-107">Parameters</span></span>

### <a name="force"></a><span data-ttu-id="9399a-108">force</span><span class="sxs-lookup"><span data-stu-id="9399a-108">force</span></span>

<span data-ttu-id="9399a-109">Se isso for **true**, a configuração atual é reaplicada, mesmo que haja uma configuração pendente.</span><span class="sxs-lookup"><span data-stu-id="9399a-109">If this is **true**, the current configuration is reapplied, even if there is a configuration pending.</span></span>

## <a name="return-value"></a><span data-ttu-id="9399a-110">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="9399a-110">Return value</span></span>

<span data-ttu-id="9399a-111">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="9399a-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="9399a-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="9399a-112">Remarks</span></span>

<span data-ttu-id="9399a-113">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="9399a-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="9399a-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9399a-114">Requirements</span></span>

<span data-ttu-id="9399a-115">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="9399a-115">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="9399a-116">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="9399a-116">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="9399a-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="9399a-117">See also</span></span>

[<span data-ttu-id="9399a-118">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="9399a-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
