---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Método GetConfigurationResultOutput
ms.openlocfilehash: 480e710ce1a208253f0e664474c3e9bab296066a
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67727120"
---
# <a name="getconfigurationresultoutput-method"></a><span data-ttu-id="4cfe4-103">Método GetConfigurationResultOutput</span><span class="sxs-lookup"><span data-stu-id="4cfe4-103">GetConfigurationResultOutput method</span></span>

<span data-ttu-id="4cfe4-104">Obtém a saída do Agente de Configuração associada a um trabalho específico.</span><span class="sxs-lookup"><span data-stu-id="4cfe4-104">Gets the Configuration Agent output associated with a specific job.</span></span>

## <a name="syntax"></a><span data-ttu-id="4cfe4-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4cfe4-105">Syntax</span></span>

```mof
uint32 GetConfigurationResultOutput(
  [in]  string                      jobId,
  [in]  uint8                       resumeOutputBookmark[],
  [out] MSFT_DSCConfigurationOutput output[]
);
```

## <a name="parameters"></a><span data-ttu-id="4cfe4-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="4cfe4-106">Parameters</span></span>

<span data-ttu-id="4cfe4-107">*jobId* \[in\] A ID do trabalho para o qual obter dados de saída.</span><span class="sxs-lookup"><span data-stu-id="4cfe4-107">*jobId* \[in\] The ID of the job for which to get output data.</span></span>

<span data-ttu-id="4cfe4-108">*resumeOutputBookmark* \[in\] Especifica que a saída deve ser uma continuação de um indicador anterior.</span><span class="sxs-lookup"><span data-stu-id="4cfe4-108">*resumeOutputBookmark* \[in\] Specifies that the output should be a continuation from a previous bookmark.</span></span>

<span data-ttu-id="4cfe4-109">*output* \[out\] A saída para o trabalho especificado.</span><span class="sxs-lookup"><span data-stu-id="4cfe4-109">*output* \[out\] The output for the specified job.</span></span>

## <a name="return-value"></a><span data-ttu-id="4cfe4-110">Retornar valor</span><span class="sxs-lookup"><span data-stu-id="4cfe4-110">Return value</span></span>

<span data-ttu-id="4cfe4-111">Retorna zero em caso de êxito; caso contrário, retorna um código de erro.</span><span class="sxs-lookup"><span data-stu-id="4cfe4-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="4cfe4-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="4cfe4-112">Remarks</span></span>

<span data-ttu-id="4cfe4-113">Esse é um método estático.</span><span class="sxs-lookup"><span data-stu-id="4cfe4-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="4cfe4-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4cfe4-114">Requirements</span></span>

<span data-ttu-id="4cfe4-115">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="4cfe4-115">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="4cfe4-116">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="4cfe4-116">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="4cfe4-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4cfe4-117">See also</span></span>

[<span data-ttu-id="4cfe4-118">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="4cfe4-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
