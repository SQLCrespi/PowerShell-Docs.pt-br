---
ms.date: 07/17/2020
keywords: DSC,powershell,configuração,instalação
title: Método RemoveConfiguration
ms.openlocfilehash: ef15c873d8dfaf28e5cdeb611b72a70921c099be
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464342"
---
# <a name="removeconfiguration-method"></a>Método RemoveConfiguration

Remove os arquivo de configuração.

## <a name="syntax"></a>Sintaxe

```mof
uint32 RemoveConfiguration(
  [in] uint32  Stage,
  [in] boolean Force
);
```

## <a name="parameters"></a>Parâmetros

**Stage** \[in\] Especifica qual documento de configuração remover. Os seguintes valores são válidos:

|Valor |Descrição |
|:--- |:---|
|**1** | O documento de configuração **atual** (current.mof). |
|**2** | O documento de configuração **Pendente** (current.mof).  |
|**4** | O documento de configuração **Anterior** (current.mof). |

*Force* \[in\] **true** para forçar a remoção da configuração.

## <a name="return-value"></a>Valor retornado

Retorna zero em caso de êxito; caso contrário, retorna um código de erro.

## <a name="remarks"></a>Comentários

Esse é um método estático.

## <a name="requirements"></a>Requisitos

**MOF:** DscCore.mof

**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>Confira também

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
