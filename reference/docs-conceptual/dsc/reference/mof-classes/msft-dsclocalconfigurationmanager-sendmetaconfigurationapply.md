---
ms.date: 07/17/2020
ms.topic: reference
title: Método SendMetaConfigurationApply
description: Método SendMetaConfigurationApply
ms.openlocfilehash: 27c58819c0249ace011c475e500e565e5daed9bb
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92648955"
---
# <a name="sendmetaconfigurationapply-method"></a>Método SendMetaConfigurationApply

Define as configurações do Gerenciador de Configurações Local usadas para controlar o Agente de Configuração.

## <a name="syntax"></a>Sintaxe

```mof
uint32 SendMetaConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a>Parâmetros

**ConfigurationData** \[in\] Os dados de ambiente da configuração.

**force** \[in\] **true** para forçar a configuração a parar.

## <a name="return-value"></a>Valor retornado

Retorna zero em caso de êxito; caso contrário, retorna um código de erro.

## <a name="remarks"></a>Comentários

Esse é um método estático.

## <a name="requirements"></a>Requisitos

**MOF:** DscCore.mof

**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>Confira também

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
