---
ms.date: 07/09/2019
keywords: DSC, GPO, PowerShell, configuração, instalação
title: Início Rápido – Converter a Política de Grupo em DSC
description: Este Início Rápido mostra as etapas necessárias para converter uma Política de Grupo do Windows em uma configuração DSC.
ms.openlocfilehash: b67f6dd2cf6c91d90fa6ac5b6367f9efc7f40ee0
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644687"
---
# <a name="quickstart-convert-group-policy-into-dsc"></a><span data-ttu-id="ad1c1-104">Início Rápido: Converter a Política de Grupo em DSC</span><span class="sxs-lookup"><span data-stu-id="ad1c1-104">Quickstart: Convert Group Policy into DSC</span></span>

> <span data-ttu-id="ad1c1-105">Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="ad1c1-105">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="ad1c1-106">Você pode gerar uma configuração DSC de uma Política de Grupo ou uma linha de base da Central de Segurança do Azure.</span><span class="sxs-lookup"><span data-stu-id="ad1c1-106">You can generate a DSC configuration from a Group Policy or Azure Security Center baseline.</span></span> <span data-ttu-id="ad1c1-107">O módulo [BaselineManagement](https://www.powershellgallery.com/packages/BaselineManagement) inclui os comandos a seguir para realizar essa tarefa.</span><span class="sxs-lookup"><span data-stu-id="ad1c1-107">The [BaselineManagement](https://www.powershellgallery.com/packages/BaselineManagement) module includes the following commands for accomplishing this task.</span></span>

- <span data-ttu-id="ad1c1-108">`ConvertFrom-GPO` – converte as Políticas de Grupo armazenadas como arquivos.</span><span class="sxs-lookup"><span data-stu-id="ad1c1-108">`ConvertFrom-GPO` - Converts Group Policies, stored as files.</span></span> <span data-ttu-id="ad1c1-109">Você também pode especificar um diretório que contém várias políticas que serão combinadas em uma única configuração.</span><span class="sxs-lookup"><span data-stu-id="ad1c1-109">You can also specify a directory containing multiple policies that will be combined into one Configuration.</span></span>
  - <span data-ttu-id="ad1c1-110">Para exportar as Políticas de Grupo em seu ambiente, use o cmdlet [Backup-GPO](/powershell/module/grouppolicy/backup-gpo) ou siga as instruções em [Exportar um GPO para um arquivo](/microsoft-desktop-optimization-pack/agpm/export-a-gpo-to-a-file).</span><span class="sxs-lookup"><span data-stu-id="ad1c1-110">To export Group Policies in your environment, use the [Backup-GPO](/powershell/module/grouppolicy/backup-gpo) cmdlet, or follow the instructions in [Export a GPO to a File](/microsoft-desktop-optimization-pack/agpm/export-a-gpo-to-a-file).</span></span>
- <span data-ttu-id="ad1c1-111">`ConvertFrom-SCM` – converte as linhas de base do Gerenciador de Conformidade de Segurança, armazenadas como `.xml` arquivos.</span><span class="sxs-lookup"><span data-stu-id="ad1c1-111">`ConvertFrom-SCM` - Converts Security Compliance Manager baselines, stored as `.xml` files.</span></span>
- <span data-ttu-id="ad1c1-112">`ConvertFrom-ASC` – converte as linhas de base da Central de Segurança do Azure, armazenadas como arquivos `.json`.</span><span class="sxs-lookup"><span data-stu-id="ad1c1-112">`ConvertFrom-ASC` - Converts Azure Security Center baselines, stored as `.json` files.</span></span>
- <span data-ttu-id="ad1c1-113">`Merge-GPOs` – converte as Políticas de Grupo aplicadas a um computador de destino.</span><span class="sxs-lookup"><span data-stu-id="ad1c1-113">`Merge-GPOs` - Converts Group Policies applied to a target computer.</span></span>

<span data-ttu-id="ad1c1-114">Os cmdlets listados acima convertem uma linha de base em um arquivo `.mof` DSC.</span><span class="sxs-lookup"><span data-stu-id="ad1c1-114">The cmdlets listed above convert a baseline into a DSC `.mof` file.</span></span> <span data-ttu-id="ad1c1-115">Você também pode optar por gerar um script de configuração (`.ps1`), que pode ser editado e recompilado.</span><span class="sxs-lookup"><span data-stu-id="ad1c1-115">You can also choose to output a Configuration script (`.ps1`), that you can edit and recompile.</span></span> <span data-ttu-id="ad1c1-116">Os cmdlets detectam erros de compilação para os recursos ausentes ou blocos de recursos duplicados.</span><span class="sxs-lookup"><span data-stu-id="ad1c1-116">The cmdlets detect compilation errors for missing resources, or duplicate resource blocks.</span></span> <span data-ttu-id="ad1c1-117">Os blocos de recursos que causam erros de compilação são comentados.</span><span class="sxs-lookup"><span data-stu-id="ad1c1-117">Resource blocks that would cause compilation errors are commented out.</span></span>

<span data-ttu-id="ad1c1-118">O exemplo a seguir converte uma [Linha de Base de Segurança da Microsoft](https://www.microsoft.com/download/details.aspx?id=55319) em um script de configuração DSC (`.ps1`) e um arquivo `.mof`.</span><span class="sxs-lookup"><span data-stu-id="ad1c1-118">The following example converts a [Microsoft Security Baseline](https://www.microsoft.com/download/details.aspx?id=55319) into a DSC configuration script (`.ps1`) and `.mof` file.</span></span>

```powershell
Install-Module BaselineManagement
Import-Module BaselineManagement
ConvertFrom-GPO -Path '.\Windows 10 Version 1903 and Windows Server Version 1903 Security Baseline\GPOs\' -OutputConfigurationScript
```

<span data-ttu-id="ad1c1-119">Depois de executar os comandos, você verá dois arquivos no diretório padrão "Output" criado no caminho atual.</span><span class="sxs-lookup"><span data-stu-id="ad1c1-119">After running the commands, you see two files in the default "Output" directory created under your current path.</span></span>

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

<span data-ttu-id="ad1c1-120">Cada nó gerenciado também precisará dos dois seguintes módulos:</span><span class="sxs-lookup"><span data-stu-id="ad1c1-120">Each managed node will also need the following two modules:</span></span>

- [<span data-ttu-id="ad1c1-121">SecurityPolicyDSC</span><span class="sxs-lookup"><span data-stu-id="ad1c1-121">SecurityPolicyDSC</span></span>](https://www.powershellgallery.com/packages/SecurityPolicyDsc)
- [<span data-ttu-id="ad1c1-122">AuditPolicyDSC</span><span class="sxs-lookup"><span data-stu-id="ad1c1-122">AuditPolicyDSC</span></span>](https://www.powershellgallery.com/packages/AuditPolicyDsc)

> [!NOTE]
> <span data-ttu-id="ad1c1-123">**BaselineManagement** é uma solução desenvolvida pela comunidade para tornar a DSC mais detectável para o Suporte, pois as soluções da comunidade são fornecidas pelos mantenedores do projeto e não pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ad1c1-123">**BaselineManagement** is a solution developed by the community to make DSC more discoverable for Support for community solutions come from the project maintainers and not from Microsoft.</span></span> <span data-ttu-id="ad1c1-124">Abra um novo problema para **BaselineManagement** no [GitHub](https://github.com/microsoft/BaselineManagement).</span><span class="sxs-lookup"><span data-stu-id="ad1c1-124">You can open a new issue for **BaselineManagement** on [GitHub](https://github.com/microsoft/BaselineManagement).</span></span>

## <a name="next-steps"></a><span data-ttu-id="ad1c1-125">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="ad1c1-125">Next steps</span></span>

- <span data-ttu-id="ad1c1-126">Para carregar o script de configuração no State Configuration da Automação do Azure, confira [Introdução](/azure/automation/automation-dsc-getting-started#importing-a-configuration-into-azure-automation).</span><span class="sxs-lookup"><span data-stu-id="ad1c1-126">To upload your configuration script into Azure Automation State Configuration, see [Getting Started](/azure/automation/automation-dsc-getting-started#importing-a-configuration-into-azure-automation).</span></span>
- <span data-ttu-id="ad1c1-127">Adicione os módulos **SecurityPolicyDSC** e **AuditPolicyDSC** à sua [Conta de Automação](/azure/automation/shared-resources/modules).</span><span class="sxs-lookup"><span data-stu-id="ad1c1-127">Add the **SecurityPolicyDSC** and **AuditPolicyDSC** modules to your [Automation Account](/azure/automation/shared-resources/modules).</span></span>
- <span data-ttu-id="ad1c1-128">Localize as configurações e recursos de DSC na [Galeria do PowerShell](https://www.powershellgallery.com/).</span><span class="sxs-lookup"><span data-stu-id="ad1c1-128">Find DSC configurations and resources in the [PowerShell Gallery](https://www.powershellgallery.com/).</span></span>
