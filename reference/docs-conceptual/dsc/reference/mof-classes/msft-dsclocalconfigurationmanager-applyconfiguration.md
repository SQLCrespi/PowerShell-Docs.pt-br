---
ms.date: 07/14/2020
ms.topic: reference
title: Método ApplyConfiguration
description: Método ApplyConfiguration
ms.openlocfilehash: aa99221b33d39c3ecc70156a11eaee10b540e2dc
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92664281"
---
# <a name="applyconfiguration-method"></a>Método ApplyConfiguration

Usa o Agente de Configuração para aplicar a configuração pendente.

Se não houver nenhuma configuração pendente, esse método reaplicará a configuração atual.

## <a name="syntax"></a>Sintaxe

```mof
uint32 ApplyConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a>Parâmetros

### <a name="force"></a>force

Se isso for **true** , a configuração atual é reaplicada, mesmo que haja uma configuração pendente.

## <a name="return-value"></a>Valor retornado

Retorna zero em caso de êxito; caso contrário, retorna um código de erro.

## <a name="remarks"></a>Comentários

Esse é um método estático.

## <a name="requirements"></a>Requisitos

**MOF:** DscCore.mof

**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>Confira também

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
