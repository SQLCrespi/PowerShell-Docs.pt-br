---
ms.date: 07/17/2020
ms.topic: reference
title: Método ResourceSet
description: Método ResourceSet
ms.openlocfilehash: 2554ff5805d7ed9518bd283565dc879a0fdfdfd0
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650694"
---
# <a name="resourceset-method"></a><span data-ttu-id="f1f96-103">Método ResourceSet</span><span class="sxs-lookup"><span data-stu-id="f1f96-103">ResourceSet method</span></span>

<span data-ttu-id="f1f96-104">Chama diretamente o método **Set** de um recurso de DSC.</span><span class="sxs-lookup"><span data-stu-id="f1f96-104">Directly calls the **Set** method of a DSC resource.</span></span>

## <a name="syntax"></a><span data-ttu-id="f1f96-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f1f96-105">Syntax</span></span>

```mof
uint32 ResourceSet(
  [in]  string  ResourceType,
  [in]  string  ModuleName,
  [in]  uint8   resourceProperty[],
  [out] boolean RebootRequired
);
```

## <a name="parameters"></a><span data-ttu-id="f1f96-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f1f96-106">Parameters</span></span>

<span data-ttu-id="f1f96-107">**ResourceType** \[in\] O nome do recurso a chamar.</span><span class="sxs-lookup"><span data-stu-id="f1f96-107">**ResourceType** \[in\] The name of the resource to call.</span></span>

<span data-ttu-id="f1f96-108">**ModuleName** \[in\] O nome do módulo que contém o recurso a chamar.</span><span class="sxs-lookup"><span data-stu-id="f1f96-108">**ModuleName** \[in\] The name of the module that contains the resource to call.</span></span>

<span data-ttu-id="f1f96-109">**resourceProperty** \[in\] Especifica o nome da propriedade do recurso e o respectivo valor em uma tabela de hash como chave e valor, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="f1f96-109">**resourceProperty** \[in\] Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="f1f96-110">Use o cmdlet [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) para descobrir as propriedades de recurso e seus tipos.</span><span class="sxs-lookup"><span data-stu-id="f1f96-110">Use the [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet to discover resource properties and their types.</span></span>

<span data-ttu-id="f1f96-111">**RebootRequired** \[out\] No retorno, essa propriedade será definida como **true** , se for necessário reiniciar o nó de destino.</span><span class="sxs-lookup"><span data-stu-id="f1f96-111">**RebootRequired** \[out\] On return, this property is set to **true** if the target node needs to be rebooted.</span></span>

## <a name="return-value"></a><span data-ttu-id="f1f96-112">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="f1f96-112">Return value</span></span>

<span data-ttu-id="f1f96-113">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="f1f96-113">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="f1f96-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="f1f96-114">Remarks</span></span>

<span data-ttu-id="f1f96-115">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="f1f96-115">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="f1f96-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f1f96-116">Requirements</span></span>

<span data-ttu-id="f1f96-117">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="f1f96-117">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="f1f96-118">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="f1f96-118">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="f1f96-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="f1f96-119">See also</span></span>

[<span data-ttu-id="f1f96-120">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="f1f96-120">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
