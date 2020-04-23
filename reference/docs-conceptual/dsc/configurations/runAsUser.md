---
ms.date: 06/12/2017
keywords: DSC,powershell,configuração,instalação
title: Usar credenciais com recursos de DSC
ms.openlocfilehash: fea2e3cad8d081c17853e127203f1d40d98c5de2
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "71953973"
---
# <a name="use-credentials-with-dsc-resources"></a><span data-ttu-id="9ef6b-103">Usar credenciais com recursos de DSC</span><span class="sxs-lookup"><span data-stu-id="9ef6b-103">Use Credentials with DSC Resources</span></span>

> <span data-ttu-id="9ef6b-104">Aplica-se a: Windows PowerShell 5.0, Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="9ef6b-104">Applies To: Windows PowerShell 5.0, Windows PowerShell 5.1</span></span>

<span data-ttu-id="9ef6b-105">Você pode executar um recurso de DSC em um conjunto específico de credenciais usando a propriedade automática **PsDscRunAsCredential** na configuração.</span><span class="sxs-lookup"><span data-stu-id="9ef6b-105">You can run a DSC resource under a specified set of credentials by using the automatic **PsDscRunAsCredential** property in the configuration.</span></span> <span data-ttu-id="9ef6b-106">Por padrão, o DSC executa cada recurso como a conta do sistema.</span><span class="sxs-lookup"><span data-stu-id="9ef6b-106">By default, DSC runs each resource as the system account.</span></span> <span data-ttu-id="9ef6b-107">Há vezes em que executar como usuário é necessário, como ao fazer a instalação de pacotes MSI em um contexto de usuário específico, ao configurar as chaves do registro do um usuário, ao acessar o diretório local específico de um usuário ou ao acessar um compartilhamento de rede.</span><span class="sxs-lookup"><span data-stu-id="9ef6b-107">There are times when running as a user is necessary, such as installing MSI packages in a specific user context, setting a user's registry keys, accessing a user's specific local directory, or accessing a network share.</span></span> <span data-ttu-id="9ef6b-108">O **SeInteractiveLogonRight** é necessário, pelo computador de destino, para as contas que você especificar para **PSDSCRunAsCredential**.</span><span class="sxs-lookup"><span data-stu-id="9ef6b-108">The **SeInteractiveLogonRight** is required, by the target machine, for any account you specify to **PSDSCRunAsCredential**.</span></span> <span data-ttu-id="9ef6b-109">Para obter mais informações, confira [Conta de direitos constantes](/windows/desktop/secauthz/account-rights-constants).</span><span class="sxs-lookup"><span data-stu-id="9ef6b-109">For more information, see [Account Rights Constants](/windows/desktop/secauthz/account-rights-constants).</span></span>

<span data-ttu-id="9ef6b-110">Cada recurso de DSC tem uma propriedade **PsDscRunAsCredential** que pode ser definida para qualquer credencial de usuário (um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential)).</span><span class="sxs-lookup"><span data-stu-id="9ef6b-110">Every DSC resource has a **PsDscRunAsCredential** property that can be set to any user credentials (a [PSCredential](/dotnet/api/system.management.automation.pscredential) object).</span></span> <span data-ttu-id="9ef6b-111">A credencial pode ser embutida em código como o valor da propriedade na configuração ou você pode definir o valor para [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential), que solicitará ao usuário uma credencial quando a configuração for compilada (para informações sobre como compilar configurações, confira [Configurações](configurations.md).</span><span class="sxs-lookup"><span data-stu-id="9ef6b-111">The credential can be hard-coded as the value of the property in the configuration, or you can set the value to [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential), which will prompt the user for a credential when the configuration is compiled (for information about compiling configurations, see [Configurations](configurations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9ef6b-112">No PowerShell 5.0, o uso da propriedade **PsDscRunAsCredential** nas configurações chamando recursos de composição não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="9ef6b-112">In PowerShell 5.0, using the **PsDscRunAsCredential** property in configurations calling composite resources was not supported.</span></span> <span data-ttu-id="9ef6b-113">No PowerShell 5.1, a propriedade **PsDscRunAsCredential** tem suporte nas configurações chamando recursos de composição.</span><span class="sxs-lookup"><span data-stu-id="9ef6b-113">In PowerShell 5.1, the **PsDscRunAsCredential** property is supported in configurations calling composite resources.</span></span> <span data-ttu-id="9ef6b-114">A propriedade **PsDscRunAsCredential** não está disponível no PowerShell 4.0.</span><span class="sxs-lookup"><span data-stu-id="9ef6b-114">The **PsDscRunAsCredential** property is not available in PowerShell 4.0.</span></span>

<span data-ttu-id="9ef6b-115">No exemplo a seguir, `Get-Credential` é usado para solicitar as credenciais do usuário.</span><span class="sxs-lookup"><span data-stu-id="9ef6b-115">In the following example, `Get-Credential` is used to prompt the user for credentials.</span></span> <span data-ttu-id="9ef6b-116">O recurso de **Registro** é usado para alterar a chave do Registro que especifica a cor da tela de fundo da janela de prompt de comando do Windows.</span><span class="sxs-lookup"><span data-stu-id="9ef6b-116">The **Registry** resource is used to change the registry key that specifies the background color for the Windows command prompt window.</span></span>

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
> <span data-ttu-id="9ef6b-117">Este exemplo pressupõe que você tenha um certificado válido em `C:\publicKeys\targetNode.cer`, e que a impressão digital desse certificado seja o valor exibido.</span><span class="sxs-lookup"><span data-stu-id="9ef6b-117">This example assumes that you have a valid certificate at `C:\publicKeys\targetNode.cer`, and that the thumbprint of that certificate is the value shown.</span></span> <span data-ttu-id="9ef6b-118">Para saber mais sobre como criptografar credenciais em arquivos MOF de configuração de DSC, confira [Proteção do arquivo MOF](../pull-server/secureMOF.md).</span><span class="sxs-lookup"><span data-stu-id="9ef6b-118">For information about encrypting credentials in DSC configuration MOF files, see [Securing the MOF file](../pull-server/secureMOF.md).</span></span>
