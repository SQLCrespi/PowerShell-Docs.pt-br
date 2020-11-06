---
ms.date: 04/19/2019
keywords: wmf,powershell,instalação
title: WMF (Windows Management Framework)
description: O WMF é um pré-requisito do Windows PowerShell. Este artigo mostra o histórico de versões do WMF e fornece informações sobre como encontrar e instalar o WMF.
ms.openlocfilehash: 339b140325befea0b28aa470d4249170937f2c37
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92654035"
---
# <a name="windows-management-framework"></a>Windows Management Framework

O WMF (Windows Management Framework) fornece uma interface de gerenciamento consistente para o Windows. O WMF fornece uma maneira perfeita de gerenciar várias versões do cliente Windows e do Windows Server. Os pacotes do instalador do WMF contêm as atualizações da funcionalidade de gerenciamento e estão disponíveis para versões mais antigas do Windows.

A instalação do WMF adiciona e/ou atualiza os seguintes recursos:

- Windows PowerShell
- DSC (Configuração de Estado Desejado) do Windows PowerShell
- ISE (Ambiente de Script Integrado) do Windows PowerShell
- Gerenciamento Remoto do Windows (WinRM)
- WMI (Instrumentação de Gerenciamento do Windows)
- Serviços Web do Windows PowerShell (Extensão do IIS do Management OData)
- SIL (Log de Inventário de Software)
- Provedor CIM do Gerenciador do Servidor

## <a name="wmf-release-notes"></a>Notas de versão do WMF

Para saber mais sobre os vários aprimoramentos do PowerShell e outros componentes de um determinado WMF, consulte os links abaixo para examinar as notas de versão:

- [Windows Management Framework 5.1](whats-new/release-notes.md#wmf-51-changes)
- [Windows Management Framework 5.0](whats-new/release-notes.md#wmf-50-changes)
- [Windows Management Framework 4.0](https://download.microsoft.com/download/3/D/6/3D61D262-8549-4769-A660-230B67E15B25/Windows%20Management%20Framework%204%200%20Release%20Notes.docx)
- [WMF 3.0](https://download.microsoft.com/download/E/7/6/E76850B8-DA6E-4FF5-8CCE-A24FC513FD16/WMF%203%20Release%20Notes.docx)

## <a name="wmf-availability-across-windows-operating-systems"></a>Disponibilidade do WMF entre sistemas operacionais Windows

|        Versão do sistema operacional         | [Windows Management Framework 5.1][]  | WMF 5.0<br>*Sem suporte* | [Windows Management Framework 4.0][]  | [WMF 3.0][]  | [WMF 2.0][]  |
| --------------------------------------- | ------------ | --------------------------- | ------------ | ------------ | ------------ |
| Windows Server 2019                     | É fornecido na caixa |                             |              |              |              |
| Windows Server 2016                     | É fornecido na caixa |                             |              |              |              |
| Windows 10                              | É fornecido na caixa | É fornecido na caixa                |              |              |              |
| Windows Server 2012 R2                  | Sim          | Sim                         | É fornecido na caixa |              |              |
| Windows 8.1                             | Sim          | Sim                         | É fornecido na caixa |              |              |
| Windows Server 2012                     | Sim          | Sim                         | Sim          | É fornecido na caixa |              |
| Windows 8<br>*Sem suporte*           |              |                             |              | É fornecido na caixa |              |
| Windows Server 2008 R2 SP1              | Sim          | Sim                         | Sim          | Sim          | É fornecido na caixa |
| Windows 7 SP1                           | Sim          | Sim                         | Sim          | Sim          | É fornecido na caixa |
| Windows Server 2008 SP2                 |              |                             |              | Sim          | Sim          |
| Windows Vista<br>*Sem suporte*       |              |                             |              |              | Sim          |
| Windows Server 2003<br>*Sem suporte* |              |                             |              |              | Sim          |
| Windows XP<br>*Sem suporte*          |              |                             |              | Sim          | Sim          |

- **É fornecido na caixa** : os recursos da versão especificada do WMF foram fornecidos na versão indicada do cliente Windows ou do Windows Server.
- **Sem suporte** : esses produtos não têm mais suporte da Microsoft. Você deve atualizar para uma nova versão compatível. Para saber mais, confira a página [Política do Ciclo de Vida da Microsoft][].

> [!NOTE]
> O instalador do WMF 5.0 não está mais disponível e não tem mais suporte. Ele foi substituído pelo WMF 5.1.

[Política do Ciclo de Vida da Microsoft]: https://support.microsoft.com/lifecycle
[Windows Management Framework 5.1]: https://aka.ms/wmf51download
[Windows Management Framework 4.0]: https://aka.ms/wmf4download
[WMF 3.0]: https://aka.ms/wmf3download
[WMF 2.0]: https://aka.ms/wmf2download
