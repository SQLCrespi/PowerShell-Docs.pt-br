---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Usar credenciais com recursos de DSC
description: A DSC permite fornecer as credenciais a uma configuração para que ela possa ser aplicada no contexto de uma conta de usuário específica, e não na conta Sistema Local.
ms.openlocfilehash: e4ca39e099afacd7cb06c4d9ef889f94deb73cee
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92645079"
---
# <a name="use-credentials-with-dsc-resources"></a><span data-ttu-id="745d6-104">Usar credenciais com recursos de DSC</span><span class="sxs-lookup"><span data-stu-id="745d6-104">Use Credentials with DSC Resources</span></span>

> <span data-ttu-id="745d6-105">Aplica-se a: Windows PowerShell 5.0, Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="745d6-105">Applies To: Windows PowerShell 5.0, Windows PowerShell 5.1</span></span>

<span data-ttu-id="745d6-106">Você pode executar um recurso de DSC em um conjunto específico de credenciais usando a propriedade automática **PsDscRunAsCredential** na configuração.</span><span class="sxs-lookup"><span data-stu-id="745d6-106">You can run a DSC resource under a specified set of credentials by using the automatic **PsDscRunAsCredential** property in the configuration.</span></span> <span data-ttu-id="745d6-107">Por padrão, o DSC executa cada recurso como a conta do sistema.</span><span class="sxs-lookup"><span data-stu-id="745d6-107">By default, DSC runs each resource as the system account.</span></span> <span data-ttu-id="745d6-108">Há vezes em que executar como usuário é necessário, como ao fazer a instalação de pacotes MSI em um contexto de usuário específico, ao configurar as chaves do registro do um usuário, ao acessar o diretório local específico de um usuário ou ao acessar um compartilhamento de rede.</span><span class="sxs-lookup"><span data-stu-id="745d6-108">There are times when running as a user is necessary, such as installing MSI packages in a specific user context, setting a user's registry keys, accessing a user's specific local directory, or accessing a network share.</span></span> <span data-ttu-id="745d6-109">O **SeInteractiveLogonRight** é necessário, pelo computador de destino, para as contas que você especificar para **PSDSCRunAsCredential**.</span><span class="sxs-lookup"><span data-stu-id="745d6-109">The **SeInteractiveLogonRight** is required, by the target machine, for any account you specify to **PSDSCRunAsCredential**.</span></span> <span data-ttu-id="745d6-110">Para obter mais informações, confira [Conta de direitos constantes](/windows/desktop/secauthz/account-rights-constants).</span><span class="sxs-lookup"><span data-stu-id="745d6-110">For more information, see [Account Rights Constants](/windows/desktop/secauthz/account-rights-constants).</span></span>

<span data-ttu-id="745d6-111">Cada recurso DSC tem uma propriedade **PsDscRunAsCredential** que pode ser definida para quaisquer credenciais de usuário (um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential)).</span><span class="sxs-lookup"><span data-stu-id="745d6-111">Every DSC resource has a **PsDscRunAsCredential** property that can be set to any user credentials (a [PSCredential](/dotnet/api/system.management.automation.pscredential) object).</span></span> <span data-ttu-id="745d6-112">A credencial pode ser embutida em código como o valor da propriedade na configuração ou você pode definir o valor para [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential), que solicitará ao usuário uma credencial quando a configuração for compilada (para informações sobre como compilar configurações, confira [Configurações](configurations.md).</span><span class="sxs-lookup"><span data-stu-id="745d6-112">The credential can be hard-coded as the value of the property in the configuration, or you can set the value to [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential), which will prompt the user for a credential when the configuration is compiled (for information about compiling configurations, see [Configurations](configurations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="745d6-113">No PowerShell 5.0, o uso da propriedade **PsDscRunAsCredential** nas configurações chamando recursos de composição não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="745d6-113">In PowerShell 5.0, using the **PsDscRunAsCredential** property in configurations calling composite resources was not supported.</span></span> <span data-ttu-id="745d6-114">No PowerShell 5.1, a propriedade **PsDscRunAsCredential** tem suporte nas configurações chamando recursos de composição.</span><span class="sxs-lookup"><span data-stu-id="745d6-114">In PowerShell 5.1, the **PsDscRunAsCredential** property is supported in configurations calling composite resources.</span></span> <span data-ttu-id="745d6-115">A propriedade **PsDscRunAsCredential** não está disponível no PowerShell 4.0.</span><span class="sxs-lookup"><span data-stu-id="745d6-115">The **PsDscRunAsCredential** property is not available in PowerShell 4.0.</span></span>

<span data-ttu-id="745d6-116">No exemplo a seguir, `Get-Credential` é usado para solicitar as credenciais do usuário.</span><span class="sxs-lookup"><span data-stu-id="745d6-116">In the following example, `Get-Credential` is used to prompt the user for credentials.</span></span> <span data-ttu-id="745d6-117">O recurso de **Registro** é usado para alterar a chave do Registro que especifica a cor da tela de fundo da janela de prompt de comando do Windows.</span><span class="sxs-lookup"><span data-stu-id="745d6-117">The **Registry** resource is used to change the registry key that specifies the background color for the Windows command prompt window.</span></span>

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
> <span data-ttu-id="745d6-118">Este exemplo pressupõe que você tenha um certificado válido em `C:\publicKeys\targetNode.cer`, e que a impressão digital desse certificado seja o valor exibido.</span><span class="sxs-lookup"><span data-stu-id="745d6-118">This example assumes that you have a valid certificate at `C:\publicKeys\targetNode.cer`, and that the thumbprint of that certificate is the value shown.</span></span> <span data-ttu-id="745d6-119">Para obter informações sobre como criptografar credenciais em arquivos MOF de configuração DSC, consulte [Protegendo o arquivo MOF](../pull-server/secureMOF.md).</span><span class="sxs-lookup"><span data-stu-id="745d6-119">For information about encrypting credentials in DSC configuration MOF files, see [Securing the MOF file](../pull-server/secureMOF.md).</span></span>
