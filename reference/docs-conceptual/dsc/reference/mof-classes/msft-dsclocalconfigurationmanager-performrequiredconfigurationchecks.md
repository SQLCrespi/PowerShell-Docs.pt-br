---
ms.date: 07/17/2020
ms.topic: reference
title: Método PerformRequiredConfigurationChecks
description: Método PerformRequiredConfigurationChecks
ms.openlocfilehash: c5e847cda6376f4266cc771dc947032a279e25f4
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650825"
---
# <a name="performrequiredconfigurationchecks-method"></a><span data-ttu-id="634f9-103">Método PerformRequiredConfigurationChecks</span><span class="sxs-lookup"><span data-stu-id="634f9-103">PerformRequiredConfigurationChecks method</span></span>

<span data-ttu-id="634f9-104">Inicia uma verificação de consistência usando o Agendador de Tarefas.</span><span class="sxs-lookup"><span data-stu-id="634f9-104">Starts a consistency check by using the Task Scheduler.</span></span>

## <a name="syntax"></a><span data-ttu-id="634f9-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="634f9-105">Syntax</span></span>

```mof
uint32 PerformRequiredConfigurationChecks(
  [in] uint32 Flags
);
```

## <a name="parameters"></a><span data-ttu-id="634f9-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="634f9-106">Parameters</span></span>

<span data-ttu-id="634f9-107">**Flags** \[in\] Um bitmask que especifica o tipo de verificação de consistência que deve ser executada.</span><span class="sxs-lookup"><span data-stu-id="634f9-107">**Flags** \[in\] A bitmask that specifies the type of consistency check to run.</span></span> <span data-ttu-id="634f9-108">Os seguintes valores são válidos e podem ser combinados usando um operação **OR** bit a bit:</span><span class="sxs-lookup"><span data-stu-id="634f9-108">The following values are valid, and can be combined by using a bitwise **OR** operation:</span></span>

|<span data-ttu-id="634f9-109">Valor</span><span class="sxs-lookup"><span data-stu-id="634f9-109">Value</span></span> |<span data-ttu-id="634f9-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="634f9-110">Description</span></span> |
|:--- |:---|
|<span data-ttu-id="634f9-111">**1**</span><span class="sxs-lookup"><span data-stu-id="634f9-111">**1**</span></span> | <span data-ttu-id="634f9-112">Uma verificação de consistência normal.</span><span class="sxs-lookup"><span data-stu-id="634f9-112">A normal consistency check.</span></span> |
|<span data-ttu-id="634f9-113">**2**</span><span class="sxs-lookup"><span data-stu-id="634f9-113">**2**</span></span> | <span data-ttu-id="634f9-114">Uma continuação de uma verificação de consistência após uma reinicialização.</span><span class="sxs-lookup"><span data-stu-id="634f9-114">A continuation of a consistency check after a reboot.</span></span> <span data-ttu-id="634f9-115">Esse valor não deve ser combinado com outros valores.</span><span class="sxs-lookup"><span data-stu-id="634f9-115">This value should not be combined with other values.</span></span> |
|<span data-ttu-id="634f9-116">**4**</span><span class="sxs-lookup"><span data-stu-id="634f9-116">**4**</span></span> | <span data-ttu-id="634f9-117">A configuração deve ser extraída do servidor de pull especificado na metaconfiguração do nó.</span><span class="sxs-lookup"><span data-stu-id="634f9-117">The configuration should be pulled from the pull server specified in the metaconfiguration for the node.</span></span> <span data-ttu-id="634f9-118">Esse valor deve sempre ser combinado com **1** , para um valor de **5** .</span><span class="sxs-lookup"><span data-stu-id="634f9-118">This value should always be combined with **1** , for a value of **5** .</span></span> |
|<span data-ttu-id="634f9-119">**8**</span><span class="sxs-lookup"><span data-stu-id="634f9-119">**8**</span></span> | <span data-ttu-id="634f9-120">Envie status para o servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="634f9-120">Send status to the report server.</span></span> |

## <a name="return-value"></a><span data-ttu-id="634f9-121">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="634f9-121">Return value</span></span>

<span data-ttu-id="634f9-122">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="634f9-122">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="634f9-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="634f9-123">Remarks</span></span>

<span data-ttu-id="634f9-124">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="634f9-124">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="634f9-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="634f9-125">Requirements</span></span>

<span data-ttu-id="634f9-126">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="634f9-126">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="634f9-127">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="634f9-127">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="634f9-128">Confira também</span><span class="sxs-lookup"><span data-stu-id="634f9-128">See also</span></span>

[<span data-ttu-id="634f9-129">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="634f9-129">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
