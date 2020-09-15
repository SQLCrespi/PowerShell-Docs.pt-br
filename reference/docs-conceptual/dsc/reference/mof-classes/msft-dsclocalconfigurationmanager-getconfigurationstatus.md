---
ms.date: 07/17/2020
keywords: DSC,powershell,configuração,instalação
title: Método GetConfigurationStatus
ms.openlocfilehash: c2c478151428052d656832fb4079f12d666a910d
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464036"
---
# <a name="getconfigurationstatus-method"></a>Método GetConfigurationStatus

Obtém o histórico do status de configuração.

## <a name="syntax"></a>Sintaxe

```mof
uint32 GetConfigurationStatus(
  [in]  boolean                     All,
  [out] MSFT_DSCConfigurationStatus configurationStatus[]
);
```

## <a name="parameters"></a>Parâmetros

**All** \[in\] **true** caso esse método deva retornar informações sobre todas as configurações executadas no computador, incluindo o aplicativo de configuração e a verificação de consistência.

**configurationStatus** \[out\] No retorno, contém uma instância inserida da classe **MSFT_DSCConfigurationStatus** que define as configurações.

## <a name="return-value"></a>Valor retornado

Retorna zero em caso de êxito; caso contrário, retorna um código de erro.

## <a name="remarks"></a>Comentários

Esse é um método estático.

## <a name="requirements"></a>Requisitos

**MOF:** DscCore.mof

**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>Confira também

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
