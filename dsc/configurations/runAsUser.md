---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Usar credenciais com recursos de DSC
ms.openlocfilehash: fea2e3cad8d081c17853e127203f1d40d98c5de2
ms.sourcegitcommit: bc42c9166857147a1ecf9924b718d4a48eb901e3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2019
ms.locfileid: "66470758"
---
# <a name="use-credentials-with-dsc-resources"></a>Usar credenciais com recursos de DSC

> Aplica-se a: Windows PowerShell 5.0, Windows PowerShell 5.1

Você pode executar um recurso de DSC em um conjunto específico de credenciais usando a propriedade automática **PsDscRunAsCredential** na configuração. Por padrão, o DSC executa cada recurso como a conta do sistema. Há vezes em que executar como usuário é necessário, como ao fazer a instalação de pacotes MSI em um contexto de usuário específico, ao configurar as chaves do registro do um usuário, ao acessar o diretório local específico de um usuário ou ao acessar um compartilhamento de rede. O **SeInteractiveLogonRight** é necessário, pelo computador de destino, para as contas que você especificar para **PSDSCRunAsCredential**. Para obter mais informações, confira [Conta de direitos constantes](/windows/desktop/secauthz/account-rights-constants).

Cada recurso de DSC tem uma propriedade **PsDscRunAsCredential** que pode ser definida para qualquer credencial de usuário (um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential)). A credencial pode ser embutida em código como o valor da propriedade na configuração ou você pode definir o valor para [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential), que solicitará ao usuário uma credencial quando a configuração for compilada (para informações sobre como compilar configurações, confira [Configurações](configurations.md).

> [!NOTE]
> No PowerShell 5.0, o uso da propriedade **PsDscRunAsCredential** nas configurações chamando recursos de composição não tem suporte. No PowerShell 5.1, a propriedade **PsDscRunAsCredential** tem suporte nas configurações chamando recursos de composição. A propriedade **PsDscRunAsCredential** não está disponível no PowerShell 4.0.

No exemplo a seguir, `Get-Credential` é usado para solicitar as credenciais do usuário. O recurso de **Registro** é usado para alterar a chave do Registro que especifica a cor da tela de fundo da janela de prompt de comando do Windows.

```powershell
Configuration ChangeCmdBackGroundColor
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration

    Node $AllNodes.NodeName
    {
        Registry CmdPath
        {
            Key                  = 'HKEY_CURRENT_USER\SOFTWARE\Microsoft\Command Processor'
            ValueName            = 'DefaultColor'
            ValueData            = '1F'
            ValueType            = 'DWORD'
            Ensure               = 'Present'
            Force                = $true
            Hex                  = $true
            PsDscRunAsCredential = Get-Credential
        }
    }
}

$configData = @{
    AllNodes = @(
        @{
            NodeName             = 'localhost';
            PSDscAllowDomainUser = $true
            CertificateFile      = 'C:\publicKeys\targetNode.cer'
            Thumbprint           = '7ee7f09d-4be0-41aa-a47f-96b9e3bdec25'
        }
    )
}

ChangeCmdBackGroundColor -ConfigurationData $configData
```

> [!NOTE]
> Este exemplo pressupõe que você tenha um certificado válido em `C:\publicKeys\targetNode.cer`, e que a impressão digital desse certificado seja o valor exibido. Para saber mais sobre como criptografar credenciais em arquivos MOF de configuração de DSC, confira [Proteção do arquivo MOF](../pull-server/secureMOF.md).
