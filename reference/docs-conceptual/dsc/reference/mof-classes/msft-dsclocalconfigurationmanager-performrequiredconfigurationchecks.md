---
ms.date: 07/17/2020
keywords: DSC,powershell,configuração,instalação
title: Método PerformRequiredConfigurationChecks
ms.openlocfilehash: ea4294ffdcb2580fa7b39b18966b642d58073eb6
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464444"
---
# <a name="performrequiredconfigurationchecks-method"></a>Método PerformRequiredConfigurationChecks

Inicia uma verificação de consistência usando o Agendador de Tarefas.

## <a name="syntax"></a>Sintaxe

```mof
uint32 PerformRequiredConfigurationChecks(
  [in] uint32 Flags
);
```

## <a name="parameters"></a>Parâmetros

**Flags** \[in\] Um bitmask que especifica o tipo de verificação de consistência que deve ser executada. Os seguintes valores são válidos e podem ser combinados usando um operação **OR** bit a bit:

|Valor |Descrição |
|:--- |:---|
|**1** | Uma verificação de consistência normal. |
|**2** | Uma continuação de uma verificação de consistência após uma reinicialização. Esse valor não deve ser combinado com outros valores. |
|**4** | A configuração deve ser extraída do servidor de pull especificado na metaconfiguração do nó. Esse valor deve sempre ser combinado com **1**, para um valor de **5**. |
|**8** | Envie status para o servidor de relatório. |

## <a name="return-value"></a>Valor retornado

Retorna zero em caso de êxito; caso contrário, retorna um código de erro.

## <a name="remarks"></a>Comentários

Esse é um método estático.

## <a name="requirements"></a>Requisitos

**MOF:** DscCore.mof

**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>Confira também

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
