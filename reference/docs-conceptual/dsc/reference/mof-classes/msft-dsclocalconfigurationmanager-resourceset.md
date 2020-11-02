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
# <a name="resourceset-method"></a>Método ResourceSet

Chama diretamente o método **Set** de um recurso de DSC.

## <a name="syntax"></a>Sintaxe

```mof
uint32 ResourceSet(
  [in]  string  ResourceType,
  [in]  string  ModuleName,
  [in]  uint8   resourceProperty[],
  [out] boolean RebootRequired
);
```

## <a name="parameters"></a>Parâmetros

**ResourceType** \[in\] O nome do recurso a chamar.

**ModuleName** \[in\] O nome do módulo que contém o recurso a chamar.

**resourceProperty** \[in\] Especifica o nome da propriedade do recurso e o respectivo valor em uma tabela de hash como chave e valor, respectivamente. Use o cmdlet [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) para descobrir as propriedades de recurso e seus tipos.

**RebootRequired** \[out\] No retorno, essa propriedade será definida como **true** , se for necessário reiniciar o nó de destino.

## <a name="return-value"></a>Valor retornado

Retorna zero em caso de êxito; caso contrário, retorna um código de erro.

## <a name="remarks"></a>Comentários

Esse é um método estático.

## <a name="requirements"></a>Requisitos

**MOF:** DscCore.mof

**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>Confira também

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
