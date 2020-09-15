---
ms.date: 07/17/2020
keywords: DSC,powershell,configuração,instalação
title: Método SendConfigurationApply
ms.openlocfilehash: 9b684790e5a7d6c7bdf074caca6040e13807f1ca
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464308"
---
# <a name="sendconfigurationapply-method"></a>Método SendConfigurationApply

Envia o documento de configuração para o nó gerenciado e usa o Agente de Configuração para aplicar a configuração.

## <a name="syntax"></a>Sintaxe

```mof
uint32 SendConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
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

**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>Confira também

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
