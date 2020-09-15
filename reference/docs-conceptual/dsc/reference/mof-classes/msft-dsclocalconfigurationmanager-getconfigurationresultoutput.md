---
ms.date: 07/17/2020
keywords: DSC,powershell,configuração,instalação
title: Método GetConfigurationResultOutput
ms.openlocfilehash: 9c81082c28b2ffcc329264d29784782deaa9779d
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464070"
---
# <a name="getconfigurationresultoutput-method"></a>Método GetConfigurationResultOutput

Obtém a saída do Agente de Configuração associada a um trabalho específico.

## <a name="syntax"></a>Sintaxe

```mof
uint32 GetConfigurationResultOutput(
  [in]  string                      jobId,
  [in]  uint8                       resumeOutputBookmark[],
  [out] MSFT_DSCConfigurationOutput output[]
);
```

## <a name="parameters"></a>Parâmetros

**jobId** \[in\] A ID do trabalho para o qual obter dados de saída.

**resumeOutputBookmark** \[in\] Especifica que a saída deve ser uma continuação de um indicador anterior.

**output** \[out\] A saída para o trabalho especificado.

## <a name="return-value"></a>Valor retornado

Retorna zero em caso de êxito; caso contrário, retorna um código de erro.

## <a name="remarks"></a>Comentários

Esse é um método estático.

## <a name="requirements"></a>Requisitos

**MOF:** DscCore.mof

**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>Confira também

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
