---
ms.date: 07/17/2020
keywords: DSC,powershell,configuração,instalação
title: Método TestConfiguration
ms.openlocfilehash: 0611c4d5543c49b879bef9b60cafdd0b055c9b86
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464291"
---
# <a name="testconfiguration-method"></a>Método TestConfiguration

Envia o documento de configuração para o nó gerenciado e verifica a configuração atual de acordo com o documento.

## <a name="syntax"></a>Sintaxe

```mof
uint32 TestConfiguration(
  [in]  uint8                          configurationData[],
  [out] boolean                        InDesiredState,
  [out] MSFT_ResourceInDesiredState    ResourcesInDesiredState[],
  [out] MSFT_ResourceNotInDesiredState ResourcesNotInDesiredState[]
);
```

## <a name="parameters"></a>Parâmetros

**configurationData** \[in\] Dados de ambiente para a configuração.

**InDesiredState** \[out\] No retorno, especifica se o nó gerenciado está no estado especificado pelo documento de configuração.

**ResourcesInDesiredState** \[out\] No retorno, contém uma instância incorporada da classe **MSFT_ResourceInDesiredState** que especifica os recursos que estão no estado desejado.

**ResourcesNotInDesiredState** \[out\] No retorno, contém uma instância inserida da classe **MSFT_ResourceNotInDesiredState** que especifica os recursos que estão no estado desejado.

## <a name="return-value"></a>Valor retornado

Retorna zero em caso de êxito; caso contrário, retorna um código de erro.

## <a name="remarks"></a>Comentários

Esse é um método estático.

## <a name="requirements"></a>Requisitos

**MOF:** DscCore.mof

**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>Confira também

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
