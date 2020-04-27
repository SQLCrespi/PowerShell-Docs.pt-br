---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Método GetConfigurationStatus
ms.openlocfilehash: 83b30ba2612d962fcf2fa658d07d18fb2d91ccc7
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "71955013"
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

*All* \[in\] **true** caso esse método deva retornar informações sobre todas as configurações executadas no computador, incluindo o aplicativo de configuração e a verificação de consistência.

*configurationStatus* \[out\] No retorno, contém uma instância inserida da classe **MSFT_DSCConfigurationStatus** que define as configurações.

## <a name="return-value"></a>Valor retornado

Retorna zero em caso de êxito; caso contrário, retorna um código de erro.

## <a name="remarks"></a>Comentários

Esse é um método estático.

## <a name="requirements"></a>Requisitos

**MOF:** DscCore.mof

**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>Confira também

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
