---
ms.date: 07/17/2020
ms.topic: reference
title: Método ResourceTest
description: Método ResourceTest
ms.openlocfilehash: cbac53ea96a59ec92fa840f75cd264a3125b965a
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650675"
---
# <a name="resourcetest-method"></a>Método ResourceTest

Chama diretamente o método **Test** de um recurso de DSC.

## <a name="syntax"></a>Sintaxe

```mof
uint32 ResourceTest(
  [in]  string  ResourceType,
  [in]  string  ModuleName,
  [in]  uint8   resourceProperty[],
  [out] boolean InDesiredState
);
```

## <a name="parameters"></a>Parâmetros

**ResourceType** \[in\] O nome do recurso a chamar.

**ModuleName** \[in\] O nome do módulo que contém o recurso a chamar.

**_resourceProperty_* \[in\] Especifica o nome da propriedade do recurso e o respectivo valor em uma tabela de hash como chave e valor, respectivamente. Use o cmdlet [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) para descobrir as propriedades de recurso e seus tipos.

*InDesiredState** \[out\] No retorno, essa propriedade será definida como **true** se o nó de destino estiver no estado desejado.

## <a name="return-value"></a>Valor retornado

Retorna zero em caso de êxito; caso contrário, retorna um código de erro.

## <a name="remarks"></a>Comentários

Esse é um método estático.

## <a name="requirements"></a>Requisitos

**MOF:** DscCore.mof

**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>Confira também

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
