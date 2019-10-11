---
ms.date: 08/15/2019
keywords: DSC,powershell,configuração,instalação
title: Introdução a DSC (Desired State Configuration) para Windows
ms.openlocfilehash: a4f9db481afda65fc4ac5e553230dbba3037ac9a
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954403"
---
# <a name="get-started-with-desired-state-configuration-dsc-for-windows"></a>Introdução a DSC (Desired State Configuration) para Windows

Este tópico explica como começar a usar a DSC (Desired State Configuration) do PowerShell para Windows.
Para obter informações gerais sobre o DSC, consulte [Introdução à Configuração de Estado Desejado do Windows PowerShell](../overview/overview.md).

## <a name="supported-windows-operation-system-versions"></a>Versões compatíveis do sistema operacional Windows

As seguintes versões são compatíveis:

- Windows Server 2019
- Windows Server 2016
- Windows Server 2012R2
- Windows Server 2012
- Windows Server 2008 R2 SP1
- Windows 10
- Windows 8.1
- Windows 7

O SKU do produto autônomo [Microsoft Hyper-V Server](/windows-server/virtualization/hyper-v/hyper-v-server-2016) não contém uma implementação da Desired State Configuration, portanto, não pode ser gerenciado pela Configuração de Estado da Automação do Azure ou DSC do PowerShell.

## <a name="installing-dsc"></a>Instalando a DSC

A Desired State Configuration do PowerShell está incluída no Windows e é atualizada por meio do Windows Management Framework.
A versão mais recente é [Windows Management Framework 5.1](https://www.microsoft.com/en-us/download/details.aspx?id=54616).

> [!NOTE]
> Não é necessário habilitar o recurso “DSC-Service” do Windows Server para gerenciar um computador usando a DSC.
> Esse recurso só é necessário ao criar uma instância de servidor de pull do Windows.

## <a name="using-dsc-for-windows"></a>Usar DSC para Windows

As seções a seguir explicam como criar e executar configurações da DSC em computadores Windows.

### <a name="creating-a-configuration-mof-document"></a>Criando um documento MOF de configuração

A palavra-chave Configuração do Windows PowerShell é usada para criar uma configuração.
As etapas a seguir descrevem a criação de um documento de configuração usando o Windows PowerShell.

#### <a name="define-a-configuration-and-generate-the-configuration-document"></a>Definir uma configuração e gerar o documento de configuração:

```powershell
Configuration EnvironmentVariable_Path
{
    param ()

    Import-DscResource -ModuleName 'PSDscResources'

    Node localhost
    {
        Environment CreatePathEnvironmentVariable
        {
            Name = 'TestPathEnvironmentVariable'
            Value = 'TestValue'
            Ensure = 'Present'
            Path = $true
            Target = @('Process', 'Machine')
        }
    }
}

EnvironmentVariable_Path -OutputPath:"C:\EnvironmentVariable_Path"
```
#### <a name="install-a-module-containing-dsc-resources"></a>Instalar um módulo que contém recursos da DSC

A Desired State Configuration do Windows PowerShell inclui módulos internos que contêm recursos da DSC.
Você também pode carregar módulos de fontes externas, como o Galeria do PowerShell, usando os cmdlets do PowerShellGet.

`Install-Module 'PSDscResources' -Verbose`

#### <a name="apply-the-configuration-to-the-machine"></a>Aplicar a configuração ao computador

Documentos de configuração (arquivos MOF) podem ser aplicados ao computador usando o cmdlet [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration).

`Start-DscConfiguration -Path 'C:\EnvironmentVariable_Path' -Wait -Verbose`

#### <a name="get-the-current-state-of-the-configuration"></a>Obter o estado atual da configuração

O cmdlet [Get-DscConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) consulta o status atual do computador e retorna os valores atuais para a configuração.

`Get-DscConfiguration`

O cmdlet [Get-DscLocalConfigurationManager](/powershell/module/psdesiredstateconfiguration/get-dscLocalConfigurationManager) retorna a metaconfiguração atual aplicada ao computador.

`Get-DscLocalConfigurationManager`

#### <a name="remove-the-current-configuration-from-a-machine"></a>Remover a configuração atual de um computador

O [Remove-DscConfigurationDocument](/powershell/module/psdesiredstateconfiguration/remove-dscconfigurationdocument)

`Remove-DscConfigurationDocument -Stage Current -Verbose`

#### <a name="configure-settings-in-local-configuration-manager"></a>Configurar o Local Configuration Manager

Aplique um arquivo MOF de metaconfiguração ao computador usando o cmdlet [Set-DSCLocalConfigurationManager](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager).
Exige o caminho até o MOF de metaconfiguração.

`Set-DSCLocalConfigurationManager -Path 'c:\metaconfig\localhost.meta.mof' -Verbose`

## <a name="windows-powershell-desired-state-configuration-log-files"></a>Arquivo de log da Desired State Configuration do Windows PowerShell

Os logs para DSC são gravados no log de eventos do Windows no caminho `Microsoft-Windows-Dsc/Operational`.
Logs adicionais para fins de depuração podem ser habilitados seguindo as etapas em [Onde ficam os logs de eventos da DSC](/powershell/dsc/troubleshooting/troubleshooting#where-are-dsc-event-logs).
