---
ms.date: 12/12/2018
keywords: DSC,powershell,configuração,instalação
title: Especificando dependências de nó cruzado
description: A DSC fornece recursos especiais que podem ser usados em configurações para especificar dependências em configurações de outros nós.
ms.openlocfilehash: a9fc09af922839b37db476c24c113efc5e3e8cb1
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92658493"
---
# <a name="specifying-cross-node-dependencies"></a>Especificando dependências de nó cruzado

> Aplica-se a: Windows PowerShell 5.0

O DSC fornece recursos especiais, **WaitForAll** , **WaitForAny** , e **WaitForSome** que podem ser usados em configurações para especificar dependências em configurações em outros nós. O comportamento desses recursos é o seguinte:

- **WaitForAll** : terá êxito se o recurso especificado estiver no estado desejado em todos os nós de destino definidos na propriedade **NodeName**.
- **WaitForAny** : terá êxito se o recurso especificado estiver no estado desejado em pelo menos um dos nós de destino definidos na propriedade **NodeName**.
- **WaitForSome** : especifica uma propriedade **NodeCount** além de uma propriedade **NodeName**. O recurso terá êxito se estiver no estado desejado em um número mínimo de nós (especificado por **NodeCount** ) definido pela propriedade **NodeName**.

## <a name="syntax"></a>Syntax

Os recursos **WaitForAll** e **WaitForAny** compartilham a mesma sintaxe. Substitua `<ResourceType>` no exemplo abaixo por **WaitForAny** ou **WaitForAll**. Como a palavra-chave **DependsOn** , você precisa formatar o nome como `[ResourceType]ResourceName`. Se o recurso pertencer a uma [Configuração](configurations.md) separada, inclua **ConfigurationName** na cadeia de caracteres formatada `[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]`. O **NodeName** é o computador, ou Nó, no qual o recurso atual deve aguardar.

```
<ResourceType> [string] #ResourceName
{
    ResourceName = [string]
    NodeName = [string]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential]]
    [ RetryCount = [Uint32] ]
    [ RetryIntervalSec = [Uint64] ]
    [ ThrottleLimit = [Uint32]]
}
```

O recurso **WaitForSome** tem uma sintaxe semelhante ao exemplo acima, mas adiciona a chave **NodeCount**. **NodeCount** indica por quantos Nós o recurso atual deve aguardar.

```
WaitForSome [String] #ResourceName
{
    NodeCount = [UInt32]
    NodeName = [string[]]
    ResourceName = [string]
    [DependsOn = [string[]]]
    [PsDscRunAsCredential = [PSCredential]]
    [RetryCount = [UInt32]]
    [RetryIntervalSec = [UInt64]]
    [ThrottleLimit = [UInt32]]
}
```

Todos os **WaitForXXXX** compartilham as chaves de sintaxe a seguir.

|       Propriedade       |                                                                           Descrição                                                                           |
| -------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| RetryIntervalSec     | O número de segundos antes de tentar novamente. O mínimo é 1.                                                                                                            |
| RetryCount           | O número máximo de tentativas.                                                                                                                           |
| ThrottleLimit        | O número de máquinas para conectar-se simultaneamente. O padrão é `New-CimSession`.                                                                              |
| DependsOn            | Indica que a configuração de outro recurso deve ser executada antes de ele ser configurado. Para obter mais informações, confira [DependsOn](resource-depends-on.md) |
| PsDscRunAsCredential | Confira [Usar DSC com credenciais do usuário](./runAsUser.md)                                                                                                           |

## <a name="using-waitforxxxx-resources"></a>Usando os recursos WaitForXXXX

Cada recurso **WaitForXXXX** aguarda os recursos especificados serem concluídos no Nó especificado.
Outros recursos na mesma Configuração podem *depender* do recurso **WaitForXXXX** usando a chave **DependsOn**.

Por exemplo, na configuração a seguir, o nó de destino aguarda que o recurso **xADDomain** seja concluído no nó **MyDC** com um número máximo de 30 novas tentativas, em intervalos de 15 segundos, antes que o nó de destino possa se unir ao domínio.

Por padrão, os recursos **WaitForXXX** realizam uma tentativa e, em seguida, falham. Embora não seja obrigatório, você geralmente deve especificar **RetryCount** e **RetryIntervalSec**.

```powershell
Configuration JoinDomain
{
    Import-DscResource -Module xComputerManagement, xActiveDirectory

    Node myDC
    {
        WindowsFeature InstallAD
        {
            Ensure = 'Present'
            Name = 'AD-Domain-Services'
        }

        xADDomain NewDomain
        {
            DomainName = 'Contoso.com'
            DomainAdministratorCredential = (Get-Credential)
            SafemodeAdministratorPassword = (Get-Credential)
            DatabasePath = "C:\Windows\NTDS"
            LogPath = "C:\Windows\NTDS"
            SysvolPath = "C:\Windows\Sysvol"
        }
    }

    Node myDomainJoinedServer
    {
        WaitForAll DC
        {
            ResourceName      = '[xADDomain]NewDomain'
            NodeName          = 'MyDC'
            RetryIntervalSec  = 15
            RetryCount        = 30
        }

        xComputer JoinDomain
        {
            Name             = 'myPC'
            DomainName       = 'Contoso.com'
            Credential       = (Get-Credential)
            DependsOn        ='[WaitForAll]DC'
        }
    }
}
```

Quando você compila a Configuração, são gerados dois arquivos ".mof". Aplique ambos os arquivos ".mof" aos Nós de destino usando o cmdlet [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration)

> [!NOTE]
> Os recursos **WaitForXXX** usam o Gerenciamento Remoto do Windows para verificar o estado dos outros nós. Para obter mais informações sobre os requisitos de porta e segurança do WinRM, confira [Considerações sobre segurança da comunicação remota do PowerShell](/powershell/scripting/learn/remoting/winrmsecurity).

## <a name="see-also"></a>Consulte Também

- [Configurações DSC](configurations.md)
- [Usar dependências do recurso](resource-depends-on.md)
- [Recursos de DSC](../resources/resources.md)
- [Configurando o Gerenciador de Configurações Local](../managing-nodes/metaConfig.md)
