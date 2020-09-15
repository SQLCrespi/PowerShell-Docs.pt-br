---
ms.date: 07/16/2020
keywords: DSC,powershell,configuração,instalação
title: Recurso de DSC WaitForAll
ms.openlocfilehash: a0cf553af96ecc3df4968581f8f393b72fc3dabf
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464359"
---
# <a name="dsc-waitforall-resource"></a>Recurso de DSC WaitForAll

> Aplica-se a: Windows PowerShell 5.x

O recurso de DSC (Desired State Configuration) **WaitForAll** pode ser usado dentro de um bloco de nó em uma [configuração DSC](../../../configurations/configurations.md) para especificar dependências em configurações em outros nós.

Esse recurso terá êxito se o recurso especificado pela propriedade **ResourceName** estiver no estado desejado em todos os nós de destino definidos na propriedade **NodeName**.

> [!NOTE]
> O recurso **WaitForAll** usa o Gerenciamento Remoto do Windows para verificar o estado dos outros nós. Para obter mais informações sobre os requisitos de porta e segurança do WinRM, confira [Considerações sobre segurança da comunicação remota do PowerShell](/powershell/scripting/learn/remoting/winrmsecurity?view=powershell-6).

## <a name="syntax"></a>Sintaxe

```Syntax
WaitForAll [string] #ResourceName
{
    ResourceName = [string]
    NodeName = [string[]]
    [ RetryIntervalSec = [Uint64] ]
    [ RetryCount = [Uint32] ]
    [ ThrottleLimit = [Uint32]]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Propriedades

|Propriedade |Descrição |
|---|---|
|ResourceName |O nome do recurso do qual dependerá. Se esse recurso pertencer a uma configuração diferente, formate o nome como `[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]`. |
|NodeName |Os nós de destino do recurso do qual dependerá. |
|RetryIntervalSec |O número de segundos antes de tentar novamente. O mínimo é 1. |
|RetryCount |O número máximo de tentativas. |
|ThrottleLimit |O número de máquinas para conectar-se simultaneamente. O padrão é `New-CimSession`. |

## <a name="common-properties"></a>Propriedades comuns

|Propriedade |Descrição |
|---|---|
|DependsOn |Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado. Por exemplo, se a ID do bloco de script de configuração do recurso que você deseja executar primeiro for ResourceName e seu tipo for ResourceType, a sintaxe para usar essa propriedade será `DependsOn = "[ResourceType]ResourceName"`. |
|PsDscRunAsCredential |Define a credencial para executar todo o recurso. |

> [!NOTE]
> A propriedade comum **PsDscRunAsCredential** foi adicionada ao WMF 5.0 para permitir a execução de qualquer recurso de DSC no contexto de outras credenciais. Para saber mais, confira [Usar credenciais com recursos de DSC](../../../configurations/runasuser.md).

## <a name="example"></a>Exemplo

Para obter um exemplo de como usar esse recurso, consulte [Especificando dependências de nó cruzado](../../../configurations/crossNodeDependencies.md)
