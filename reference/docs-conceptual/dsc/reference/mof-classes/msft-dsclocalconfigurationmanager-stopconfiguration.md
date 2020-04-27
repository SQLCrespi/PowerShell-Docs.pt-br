---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Método StopConfiguration
ms.openlocfilehash: e1de175032a3bddf11af218bc4a15bdbe554a9d5
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "71953353"
---
# <a name="stopconfiguration-method"></a>Método StopConfiguration

Interrompe a alteração da configuração em andamento.

## <a name="syntax"></a>Sintaxe

```mof
uint32 StopConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a>Parâmetros

*force* \[in\] **true** para forçar a configuração a parar.

## <a name="return-value"></a>Valor retornado

Retorna zero em caso de êxito; caso contrário, retorna um código de erro.

## <a name="remarks"></a>Comentários

Esse é um método estático.

## <a name="requirements"></a>Requisitos

**MOF:** DscCore.mof

**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>Confira também

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
