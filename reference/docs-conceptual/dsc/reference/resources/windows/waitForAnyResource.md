---
ms.date: 09/20/2019
keywords: DSC,powershell,configuração,instalação
title: Recurso de DSC WaitForAny
ms.openlocfilehash: 181760ba0a4f493c451dafb68e7881adda2d58c0
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560773"
---
# <a name="dsc-waitforany-resource"></a>Recurso de DSC WaitForAny

> Aplica-se a: Windows PowerShell 5.1

O recurso de DSC (Desired State Configuration) **WaitForAny** pode ser usado dentro de um bloco de nó em uma [configuração DSC](../../../configurations/configurations.md) para especificar dependências de configurações em outros nós.

Esse recurso terá êxito se o recurso especificado pela propriedade **ResourceName** estiver no estado desejado em qualquer nó de destino definido na propriedade **NodeName**.

> [!NOTE]
> O recurso **WaitForAny** usa o Gerenciamento Remoto do Windows para verificar o estado dos outros nós. Para obter mais informações sobre os requisitos de porta e segurança do WinRM, confira [Considerações sobre segurança da comunicação remota do PowerShell](/powershell/scripting/learn/remoting/winrmsecurity?view=powershell-6).

## <a name="syntax"></a>Sintaxe

```Syntax
WaitForAny [string] #ResourceName
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
