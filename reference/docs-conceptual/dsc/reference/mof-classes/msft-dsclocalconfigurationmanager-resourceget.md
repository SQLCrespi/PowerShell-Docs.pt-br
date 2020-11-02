---
ms.date: 07/17/2020
ms.topic: reference
title: Método ResourceGet
description: Método ResourceGet
ms.openlocfilehash: bff737f04e02740fa09fd82d7b27c75b11303dad
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650758"
---
# <a name="resourceget-method"></a><span data-ttu-id="3cad4-103">Método ResourceGet</span><span class="sxs-lookup"><span data-stu-id="3cad4-103">ResourceGet method</span></span>

<span data-ttu-id="3cad4-104">Chama diretamente o método **Get** de um recurso de DSC.</span><span class="sxs-lookup"><span data-stu-id="3cad4-104">Directly calls the **Get** method of a DSC resource.</span></span>

## <a name="syntax"></a><span data-ttu-id="3cad4-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3cad4-105">Syntax</span></span>

```mof
uint32 ResourceGet(
  [in]  string           ResourceType,
  [in]  string           ModuleName,
  [in]  uint8            resourceProperty[],
  [out] OMI_BaseResource configurations
);
```

## <a name="parameters"></a><span data-ttu-id="3cad4-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="3cad4-106">Parameters</span></span>

<span data-ttu-id="3cad4-107">**ResourceType** \[in\] O nome do recurso a chamar.</span><span class="sxs-lookup"><span data-stu-id="3cad4-107">**ResourceType** \[in\] The name of the resource to call.</span></span>

<span data-ttu-id="3cad4-108">**ModuleName** \[in\] O nome do módulo que contém o recurso a chamar.</span><span class="sxs-lookup"><span data-stu-id="3cad4-108">**ModuleName** \[in\] The name of the module that contains the resource to call.</span></span>

<span data-ttu-id="3cad4-109">**resourceProperty** \[in\] Especifica o nome da propriedade do recurso e o respectivo valor em uma tabela de hash como chave e valor, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="3cad4-109">**resourceProperty** \[in\] Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="3cad4-110">Use o cmdlet [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) para descobrir as propriedades de recurso e seus tipos.</span><span class="sxs-lookup"><span data-stu-id="3cad4-110">Use the [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet to discover resource properties and their types.</span></span>

<span data-ttu-id="3cad4-111">**configurations** \[out\] No retorno, contém uma instância inserida das configurações.</span><span class="sxs-lookup"><span data-stu-id="3cad4-111">**configurations** \[out\] On return, contains an embedded instance of the configurations.</span></span>

## <a name="return-value"></a><span data-ttu-id="3cad4-112">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="3cad4-112">Return value</span></span>

<span data-ttu-id="3cad4-113">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="3cad4-113">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="3cad4-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="3cad4-114">Remarks</span></span>

<span data-ttu-id="3cad4-115">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="3cad4-115">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="3cad4-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3cad4-116">Requirements</span></span>

<span data-ttu-id="3cad4-117">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="3cad4-117">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="3cad4-118">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="3cad4-118">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="3cad4-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="3cad4-119">See also</span></span>

[<span data-ttu-id="3cad4-120">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="3cad4-120">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
