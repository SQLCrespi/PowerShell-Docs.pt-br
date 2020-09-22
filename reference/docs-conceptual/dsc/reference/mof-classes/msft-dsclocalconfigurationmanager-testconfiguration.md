---
ms.date: 07/17/2020
keywords: DSC,powershell,configuração,instalação
title: Método TestConfiguration
ms.openlocfilehash: 0611c4d5543c49b879bef9b60cafdd0b055c9b86
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464291"
---
# <a name="testconfiguration-method"></a><span data-ttu-id="7546b-103">Método TestConfiguration</span><span class="sxs-lookup"><span data-stu-id="7546b-103">TestConfiguration method</span></span>

<span data-ttu-id="7546b-104">Envia o documento de configuração para o nó gerenciado e verifica a configuração atual de acordo com o documento.</span><span class="sxs-lookup"><span data-stu-id="7546b-104">Sends the configuration document to the managed node and verifies the current configuration against the document.</span></span>

## <a name="syntax"></a><span data-ttu-id="7546b-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7546b-105">Syntax</span></span>

```mof
uint32 TestConfiguration(
  [in]  uint8                          configurationData[],
  [out] boolean                        InDesiredState,
  [out] MSFT_ResourceInDesiredState    ResourcesInDesiredState[],
  [out] MSFT_ResourceNotInDesiredState ResourcesNotInDesiredState[]
);
```

## <a name="parameters"></a><span data-ttu-id="7546b-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="7546b-106">Parameters</span></span>

<span data-ttu-id="7546b-107">**configurationData** \[in\] Dados de ambiente para a configuração.</span><span class="sxs-lookup"><span data-stu-id="7546b-107">**configurationData** \[in\] Environment data for the configuration.</span></span>

<span data-ttu-id="7546b-108">**InDesiredState** \[out\] No retorno, especifica se o nó gerenciado está no estado especificado pelo documento de configuração.</span><span class="sxs-lookup"><span data-stu-id="7546b-108">**InDesiredState** \[out\] On return, specifies whether the managed node is in the state specified by the configuration document.</span></span>

<span data-ttu-id="7546b-109">**ResourcesInDesiredState** \[out\] No retorno, contém uma instância incorporada da classe **MSFT_ResourceInDesiredState** que especifica os recursos que estão no estado desejado.</span><span class="sxs-lookup"><span data-stu-id="7546b-109">**ResourcesInDesiredState** \[out\] On return, contains an embedded instance of the **MSFT_ResourceInDesiredState** class that specifies resources that are in the desired state.</span></span>

<span data-ttu-id="7546b-110">**ResourcesNotInDesiredState** \[out\] No retorno, contém uma instância inserida da classe **MSFT_ResourceNotInDesiredState** que especifica os recursos que estão no estado desejado.</span><span class="sxs-lookup"><span data-stu-id="7546b-110">**ResourcesNotInDesiredState** \[out\] On return, contains an embedded instance of the **MSFT_ResourceNotInDesiredState** class that specifies resources that are not in the desired state.</span></span>

## <a name="return-value"></a><span data-ttu-id="7546b-111">Valor retornado</span><span class="sxs-lookup"><span data-stu-id="7546b-111">Return value</span></span>

<span data-ttu-id="7546b-112">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="7546b-112">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="7546b-113">Comentários</span><span class="sxs-lookup"><span data-stu-id="7546b-113">Remarks</span></span>

<span data-ttu-id="7546b-114">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="7546b-114">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="7546b-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7546b-115">Requirements</span></span>

<span data-ttu-id="7546b-116">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="7546b-116">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="7546b-117">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="7546b-117">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="7546b-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="7546b-118">See also</span></span>

[<span data-ttu-id="7546b-119">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="7546b-119">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
