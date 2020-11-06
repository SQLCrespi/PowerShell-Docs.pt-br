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
# <a name="quickstart-convert-group-policy-into-dsc"></a>Início Rápido: Converter a Política de Grupo em DSC

> Aplica-se a: Windows PowerShell 4.0, Windows PowerShell 5.0

Você pode gerar uma configuração DSC de uma Política de Grupo ou uma linha de base da Central de Segurança do Azure. O módulo [BaselineManagement](https://www.powershellgallery.com/packages/BaselineManagement) inclui os comandos a seguir para realizar essa tarefa.

- `ConvertFrom-GPO` – converte as Políticas de Grupo armazenadas como arquivos. Você também pode especificar um diretório que contém várias políticas que serão combinadas em uma única configuração.
  - Para exportar as Políticas de Grupo em seu ambiente, use o cmdlet [Backup-GPO](/powershell/module/grouppolicy/backup-gpo) ou siga as instruções em [Exportar um GPO para um arquivo](/microsoft-desktop-optimization-pack/agpm/export-a-gpo-to-a-file).
- `ConvertFrom-SCM` – converte as linhas de base do Gerenciador de Conformidade de Segurança, armazenadas como `.xml` arquivos.
- `ConvertFrom-ASC` – converte as linhas de base da Central de Segurança do Azure, armazenadas como arquivos `.json`.
- `Merge-GPOs` – converte as Políticas de Grupo aplicadas a um computador de destino.

Os cmdlets listados acima convertem uma linha de base em um arquivo `.mof` DSC. Você também pode optar por gerar um script de configuração (`.ps1`), que pode ser editado e recompilado. Os cmdlets detectam erros de compilação para os recursos ausentes ou blocos de recursos duplicados. Os blocos de recursos que causam erros de compilação são comentados.

O exemplo a seguir converte uma [Linha de Base de Segurança da Microsoft](https://www.microsoft.com/download/details.aspx?id=55319) em um script de configuração DSC (`.ps1`) e um arquivo `.mof`.

```powershell
Install-Module BaselineManagement
Import-Module BaselineManagement
ConvertFrom-GPO -Path '.\Windows 10 Version 1903 and Windows Server Version 1903 Security Baseline\GPOs\' -OutputConfigurationScript
```

Depois de executar os comandos, você verá dois arquivos no diretório padrão "Output" criado no caminho atual.

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

Cada nó gerenciado também precisará dos dois seguintes módulos:

- [SecurityPolicyDSC](https://www.powershellgallery.com/packages/SecurityPolicyDsc)
- [AuditPolicyDSC](https://www.powershellgallery.com/packages/AuditPolicyDsc)

> [!NOTE]
> **BaselineManagement** é uma solução desenvolvida pela comunidade para tornar a DSC mais detectável para o Suporte, pois as soluções da comunidade são fornecidas pelos mantenedores do projeto e não pela Microsoft. Abra um novo problema para **BaselineManagement** no [GitHub](https://github.com/microsoft/BaselineManagement).

## <a name="next-steps"></a>Próximas etapas

- Para carregar o script de configuração no State Configuration da Automação do Azure, confira [Introdução](/azure/automation/automation-dsc-getting-started#importing-a-configuration-into-azure-automation).
- Adicione os módulos **SecurityPolicyDSC** e **AuditPolicyDSC** à sua [Conta de Automação](/azure/automation/shared-resources/modules).
- Localize as configurações e recursos de DSC na [Galeria do PowerShell](https://www.powershellgallery.com/).
