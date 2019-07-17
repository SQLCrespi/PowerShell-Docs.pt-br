---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Método ApplyConfiguration
ms.openlocfilehash: 0425b9a7db37e421830ba37da8f5c0a4877a1b72
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67727185"
---
# <a name="applyconfiguration-method"></a>Método ApplyConfiguration

Usa o Agente de Configuração para aplicar a configuração pendente.

Se não houver nenhuma configuração pendente, esse método reaplicará a configuração atual.

## <a name="syntax"></a>Sintaxe

```mof
uint32 ApplyConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a>Parâmetros

*force* \[in\] Se for **true**, a configuração atual será reaplicada, mesmo que haja uma configuração pendente.

## <a name="return-value"></a>Retornar valor

Retorna zero em caso de êxito; caso contrário, retorna um código de erro.

## <a name="remarks"></a>Comentários

Esse é um método estático.

## <a name="requirements"></a>Requisitos

**MOF:** DscCore.mof

**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>Consulte também

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
