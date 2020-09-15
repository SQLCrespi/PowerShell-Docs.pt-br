---
ms.date: 07/17/2020
keywords: DSC,powershell,configuração,instalação
title: Método EnableDebugConfiguration
ms.openlocfilehash: be75b1012f49db79eb75a68c6912ffd5772bf16f
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464087"
---
# <a name="enabledebugconfiguration-method"></a>Método EnableDebugConfiguration

Habilita a depuração do recurso DSC.

## <a name="syntax"></a>Sintaxe

```mof
uint32 EnableDebugConfiguration(
  [in] boolean BreakAll
);
```

## <a name="parameters"></a>Parâmetros

**BreakAll** \[in\] Define um ponto de interrupção em cada linha do script de recurso.

## <a name="return-value"></a>Valor retornado

Retorna zero em caso de êxito; caso contrário, retorna um código de erro.

## <a name="remarks"></a>Comentários

Esse é um método estático.

## <a name="requirements"></a>Requisitos

**MOF:** DscCore.mof

**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>Confira também

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
