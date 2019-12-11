---
ms.date: 07/09/2019
keywords: DSC, GPO, PowerShell, configuração, instalação
title: Início Rápido – Converter a Política de Grupo em DSC
ms.openlocfilehash: 8c89dbbce5b2b146194b799d7e36ecce3105bfeb
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "71953463"
---
> <span data-ttu-id="6c755-103">Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="6c755-103">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

# <a name="quickstart-convert-group-policy-into-dsc"></a><span data-ttu-id="6c755-104">Início Rápido: Converter a Política de Grupo em DSC</span><span class="sxs-lookup"><span data-stu-id="6c755-104">Quickstart: Convert Group Policy into DSC</span></span>

<span data-ttu-id="6c755-105">Você pode gerar uma configuração DSC de uma Política de Grupo ou uma linha de base da Central de Segurança do Azure.</span><span class="sxs-lookup"><span data-stu-id="6c755-105">You can generate a DSC configuration from a Group Policy or Azure Security Center baseline.</span></span> <span data-ttu-id="6c755-106">O módulo [BaselineManagement](https://www.powershellgallery.com/packages/BaselineManagement) inclui os comandos a seguir para realizar essa tarefa.</span><span class="sxs-lookup"><span data-stu-id="6c755-106">The [BaselineManagement](https://www.powershellgallery.com/packages/BaselineManagement) module includes the following commands for accomplishing this task.</span></span>

- <span data-ttu-id="6c755-107">`ConvertFrom-GPO` – converte as Políticas de Grupo armazenadas como arquivos.</span><span class="sxs-lookup"><span data-stu-id="6c755-107">`ConvertFrom-GPO` - Converts Group Policies, stored as files.</span></span> <span data-ttu-id="6c755-108">Você também pode especificar um diretório que contém várias políticas que serão combinadas em uma única configuração.</span><span class="sxs-lookup"><span data-stu-id="6c755-108">You can also specify a directory containing multiple policies that will be combined into one Configuration.</span></span>
  - <span data-ttu-id="6c755-109">Para exportar as Políticas de Grupo em seu ambiente, use o cmdlet [Backup-GPO](/powershell/module/grouppolicy/backup-gpo?view=win10-ps) ou siga as instruções em [Exportar um GPO para um arquivo](/microsoft-desktop-optimization-pack/agpm/export-a-gpo-to-a-file).</span><span class="sxs-lookup"><span data-stu-id="6c755-109">To export Group Policies in your environment, use the [Backup-GPO](/powershell/module/grouppolicy/backup-gpo?view=win10-ps) cmdlet, or follow the instructions in [Export a GPO to a File](/microsoft-desktop-optimization-pack/agpm/export-a-gpo-to-a-file).</span></span>
- <span data-ttu-id="6c755-110">`ConvertFrom-SCM` – converte as linhas de base do Gerenciador de Conformidade de Segurança, armazenadas como `.xml` arquivos.</span><span class="sxs-lookup"><span data-stu-id="6c755-110">`ConvertFrom-SCM` - Converts Security Compliance Manager baselines, stored as `.xml` files.</span></span>
- <span data-ttu-id="6c755-111">`ConvertFrom-ASC` – converte as linhas de base da Central de Segurança do Azure, armazenadas como arquivos `.json`.</span><span class="sxs-lookup"><span data-stu-id="6c755-111">`ConvertFrom-ASC` - Converts Azure Security Center baselines, stored as `.json` files.</span></span>
- <span data-ttu-id="6c755-112">`Merge-GPOs` – converte as Políticas de Grupo aplicadas a um computador de destino.</span><span class="sxs-lookup"><span data-stu-id="6c755-112">`Merge-GPOs` - Converts Group Policies applied to a target computer.</span></span>

<span data-ttu-id="6c755-113">Os cmdlets listados acima convertem uma linha de base em um arquivo `.mof` DSC.</span><span class="sxs-lookup"><span data-stu-id="6c755-113">The cmdlets listed above convert a baseline into a DSC `.mof` file.</span></span> <span data-ttu-id="6c755-114">Você também pode optar por gerar um script de configuração (`.ps1`), que pode ser editado e recompilado.</span><span class="sxs-lookup"><span data-stu-id="6c755-114">You can also choose to output a Configuration script (`.ps1`), that you can edit and recompile.</span></span> <span data-ttu-id="6c755-115">Os cmdlets detectam erros de compilação para os recursos ausentes ou blocos de recursos duplicados.</span><span class="sxs-lookup"><span data-stu-id="6c755-115">The cmdlets detect compilation errors for missing resources, or duplicate resource blocks.</span></span> <span data-ttu-id="6c755-116">Os blocos de recursos que causam erros de compilação são comentados.</span><span class="sxs-lookup"><span data-stu-id="6c755-116">Resource blocks that would cause compilation errors are commented out.</span></span>

<span data-ttu-id="6c755-117">O exemplo a seguir converte uma [Linha de Base de Segurança da Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=55319) em um script de configuração DSC (`.ps1`) e um arquivo `.mof`.</span><span class="sxs-lookup"><span data-stu-id="6c755-117">The following example converts a [Microsoft Security Baseline](https://www.microsoft.com/en-us/download/details.aspx?id=55319) into a DSC configuration script (`.ps1`) and `.mof` file.</span></span>

```powershell
Install-Module BaselineManagement
Import-Module BaselineManagement
ConvertFrom-GPO -Path '.\Windows 10 Version 1903 and Windows Server Version 1903 Security Baseline\GPOs\' -OutputConfigurationScript
```

<span data-ttu-id="6c755-118">Depois de executar os comandos, você verá dois arquivos no diretório padrão "Output" criado no caminho atual.</span><span class="sxs-lookup"><span data-stu-id="6c755-118">After running the commands, you see two files in the default "Output" directory created under your current path.</span></span>

```powershell
Get-ChildItem -Path .\Output
```

```Output
    Directory:  C:\Temp

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a----         7/9/2019   9:35 AM   227.37KB DSCFromGPO.ps1
-a----         7/9/2019   9:35 AM   410.03KB localhost.mof
```

<span data-ttu-id="6c755-119">Cada nó gerenciado também precisará dos dois seguintes módulos:</span><span class="sxs-lookup"><span data-stu-id="6c755-119">Each managed node will also need the following two modules:</span></span>

- [<span data-ttu-id="6c755-120">SecurityPolicyDSC</span><span class="sxs-lookup"><span data-stu-id="6c755-120">SecurityPolicyDSC</span></span>](https://www.powershellgallery.com/packages/SecurityPolicyDsc)
- [<span data-ttu-id="6c755-121">AuditPolicyDSC</span><span class="sxs-lookup"><span data-stu-id="6c755-121">AuditPolicyDSC</span></span>](https://www.powershellgallery.com/packages/AuditPolicyDsc)

> [!NOTE]
> <span data-ttu-id="6c755-122">**BaselineManagement** é uma solução desenvolvida pela comunidade para tornar a DSC mais detectável para o Suporte, pois as soluções da comunidade são fornecidas pelos mantenedores do projeto e não pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6c755-122">**BaselineManagement** is a solution developed by the community to make DSC more discoverable for Support for community solutions come from the project maintainers and not from Microsoft.</span></span> <span data-ttu-id="6c755-123">Abra um novo problema para **BaselineManagement** no [GitHub](https://github.com/microsoft/BaselineManagement).</span><span class="sxs-lookup"><span data-stu-id="6c755-123">You can open a new issue for **BaselineManagement** on [GitHub](https://github.com/microsoft/BaselineManagement).</span></span>

## <a name="next-steps"></a><span data-ttu-id="6c755-124">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="6c755-124">Next steps</span></span>

- <span data-ttu-id="6c755-125">Para carregar o script de configuração no State Configuration da Automação do Azure, confira [Introdução](/automation/automation-dsc-getting-started#importing-a-configuration-into-azure-automation).</span><span class="sxs-lookup"><span data-stu-id="6c755-125">To upload your configuration script into Azure Automation State Configuration, see [Getting Started](/automation/automation-dsc-getting-started#importing-a-configuration-into-azure-automation).</span></span>
- <span data-ttu-id="6c755-126">Adicione os módulos **SecurityPolicyDSC** e **AuditPolicyDSC** à sua [Conta de Automação](/azure/automation/shared-resources/modules).</span><span class="sxs-lookup"><span data-stu-id="6c755-126">Add the **SecurityPolicyDSC** and **AuditPolicyDSC** modules to your [Automation Account](/azure/automation/shared-resources/modules).</span></span>
- <span data-ttu-id="6c755-127">Localize as configurações e recursos de DSC na [Galeria do PowerShell](https://www.powershellgallery.com/).</span><span class="sxs-lookup"><span data-stu-id="6c755-127">Find DSC configurations and resources in the [PowerShell Gallery](https://www.powershellgallery.com/).</span></span>
