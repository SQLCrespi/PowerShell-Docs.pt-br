---
ms.date: 12/06/2019
keywords: powershell, cmdlet
title: Requisitos do Sistema do Windows PowerShell
description: Este artigo lista os requisitos do sistema para o Windows PowerShell 3.0, o Windows PowerShell 4.0, o Windows PowerShell 5.0 e o Windows PowerShell 5.1.
ms.openlocfilehash: a82c0b1d6bf53e4a97db8414050a122ae5b7745d
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92663830"
---
# <a name="windows-powershell-system-requirements"></a>Requisitos do Sistema do Windows PowerShell

Este artigo lista os requisitos do sistema para o Windows PowerShell 3.0, o Windows PowerShell 4.0, o Windows PowerShell 5.0 e o Windows PowerShell 5.1. Além disso, recursos especiais, como o ISE (Ambiente de Script Integrado) do Windows PowerShell, comandos CIM e fluxos de trabalho.

O Windows&reg; 8.1 e o Windows Server&reg; 2012 R2 incluem todos os programas necessários. Este artigo foi projetado para usuários de versões anteriores do Windows.

## <a name="operating-system-requirements"></a>Requisitos do sistema operacional

### <a name="windows-powershell-51"></a>Windows PowerShell 5.1

O Windows PowerShell 5.1 é executado nas seguintes versões do Windows. Para executar o Windows PowerShell 5.1, instale o Windows Management Framework 5.1. Para obter mais informações, confira [Instalar e configurar WMF 5.1](../wmf/setup/install-configure.md).

|              Versão do Windows               |                           Requisito do sistema                            |
| ------------------------------------------ | ----------------------------------------------------------------------- |
| Windows Server 2019                        | Instalado por padrão                                                    |
| Windows Server 2016                        | Instalado por padrão                                                    |
| Windows Server 2012 R2                     | Instalar o [Windows Management Framework 5.1](https://aka.ms/wmf5download) |
| Windows Server 2012                        | Instalar o [Windows Management Framework 5.1](https://aka.ms/wmf5download) |
| Windows Server 2008 R2 com Service Pack 1 | Instalar o [Windows Management Framework 5.1](https://aka.ms/wmf5download) |
| Windows 10 versão 1607 e posterior             | Instalado por padrão                                                    |
| Windows 10 versão 1507 e 1511              | Instalar o [Windows Management Framework 5.1](https://aka.ms/wmf5download) |
| Windows 8.1                                | Instalar o [Windows Management Framework 5.1](https://aka.ms/wmf5download) |
| Windows 7 com Service Pack 1              | Instalar o [Windows Management Framework 5.1](https://aka.ms/wmf5download) |

### <a name="windows-powershell-50"></a>Windows PowerShell 5.0

O Windows PowerShell 5.0 é executado nas seguintes versões do Windows. Para executar o Windows PowerShell 5.0, instale o Windows Management Framework 5.1. Para obter mais informações, confira [Instalar e configurar WMF 5.1](../wmf/setup/install-configure.md). O Windows Management Framework 5.1 substitui o Windows Management Framework 5.0.

|              Versão do Windows               |                           Requisito do sistema                            |
| ------------------------------------------ | ----------------------------------------------------------------------- |
| Windows Server 2019                        | Versão posterior instalada por padrão                                     |
| Windows Server 2016                        | Versão posterior instalada por padrão                                     |
| Windows Server 2012 R2                     | Instalar o [Windows Management Framework 5.1](https://aka.ms/wmf5download) |
| Windows Server 2012                        | Instalar o [Windows Management Framework 5.1](https://aka.ms/wmf5download) |
| Windows Server 2008 R2 com Service Pack 1 | Instalar o [Windows Management Framework 5.1](https://aka.ms/wmf5download) |
| Windows 10 versão 1607 e posterior             | Versão posterior instalada por padrão                                     |
| Windows 10 versão 1507 e 1511              | Instalado por padrão                                                    |
| Windows 8.1                                | Instalar o [Windows Management Framework 5.1](https://aka.ms/wmf5download) |
| Windows 7 com Service Pack 1              | Instalar o [Windows Management Framework 5.1](https://aka.ms/wmf5download) |

### <a name="windows-powershell-40"></a>Windows PowerShell 4.0

O Windows PowerShell 4.0 é executado nas seguintes versões do Windows. Para executar o Windows PowerShell 4.0, instale a versão especificada do Windows Management Framework para seu sistema operacional.

|               Versão do Windows               |                                             Requisito do sistema                                             |
| ------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| Windows 8.1                                 | Instalado por padrão                                                                                       |
| Windows Server 2012 R2                      | Instalado por padrão                                                                                       |
| Windows&reg; 7 com Service Pack 1              | Instalar o [Windows Management Framework 4.0](https://www.microsoft.com/download/details.aspx?id=40855) |
| Windows Server&reg; 2008 R2 com Service Pack 1 | Instalar o [Windows Management Framework 4.0](https://www.microsoft.com/download/details.aspx?id=40855) |

### <a name="windows-powershell-30"></a>Windows PowerShell 3.0

O Windows PowerShell 3.0 é executado nas seguintes versões do Windows. Para executar o Windows PowerShell 3.0, instale a versão especificada do Windows Management Framework para seu sistema operacional.

|               Versão do Windows               |                                             Requisito do sistema                                             |
| ------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| Windows 8                                   | Instalado por padrão                                                                                       |
| Windows Server 2012                         | Instalado por padrão                                                                                       |
| Windows&reg; 7 com Service Pack 1              | Instalar o [Windows Management Framework 3.0](https://www.microsoft.com/download/details.aspx?id=34595) |
| Windows Server&reg; 2008 R2 com Service Pack 1 | Instalar o [Windows Management Framework 3.0](https://www.microsoft.com/download/details.aspx?id=34595) |
| Windows Server 2008 com Service Pack 2     | Instalar o [Windows Management Framework 3.0](https://www.microsoft.com/download/details.aspx?id=34595) |

## <a name="microsoft-net-framework-requirements"></a>Requisitos do Microsoft .NET Framework

A tabela a seguir mostra os requisitos do .NET Framework para o Windows PowerShell.

|        Versão         |                                                                                 Requisito do .NET                                                                                  |
| ---------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Windows PowerShell 5.1 | Exige a instalação completa do Microsoft .NET Framework 4.5. O Windows 8.1 e o Windows Server 2012 R2 incluem o Microsoft .NET Framework 4.5 por padrão.                           |
| Windows PowerShell 5.0 | Exige a instalação completa do Microsoft .NET Framework 4.5. O Windows 8.1 e o Windows Server 2012 R2 incluem o Microsoft .NET Framework 4.5 por padrão.                           |
| Windows PowerShell 4.0 | Exige a instalação completa do Microsoft .NET Framework 4.5. O Windows 8.1 e o Windows Server 2012 R2 incluem o Microsoft .NET Framework 4.5 por padrão.                           |
| Windows PowerShell 3.0 | Exige a instalação completa do Microsoft .NET Framework 4. O Windows 8 e o Windows Server 2012 incluem o Microsoft .NET Framework 4.5 por padrão, o que atende a esse requisito. |

Use os links a seguir para baixar o Microsoft .NET Framework no Centro de Download da Microsoft.

|                     Versão                      |                                                     Link                                                     |
| ------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ |
| .NET Framework 4.5 (`dotNetFx45_Full_setup.exe`) | [Microsoft .NET Framework 4.5](https://go.microsoft.com/fwlink/?LinkID=242919)                               |
| .NET Framework 4 (`dotNetFx40_Full_setup.exe`)   | [Microsoft .NET Framework 4 (Web Installer)](https://www.microsoft.com/download/details.aspx?id=17851) |

## <a name="windows-management-framework-40"></a>Windows Management Framework 4.0

O Windows PowerShell 5.0 requer que o Windows Management Framework 4.0 esteja pré-instalado no Windows Server 2008 R2 SP1 e Windows 7 SP1.

## <a name="ws-management-30"></a>WS-Management 3.0

O Windows PowerShell 3.0 e Windows PowerShell 4.0 requerem o WS-Management 3.0, que dá suporte ao serviço WinRM e ao protocolo WSMan. Esse programa está incluído no Windows 8.1, Windows Server 2012 R2, Windows 8, Windows Server 2012, Windows Management Framework 4.0 e Windows Management Framework 3.0.

## <a name="windows-management-instrumentation-30"></a>Instrumentação de Gerenciamento do Windows 3.0

O Windows PowerShell 3.0 e o Windows PowerShell 4.0 exigem a WMI (Instrumentação de Gerenciamento do Windows) 3.0. Esse programa está incluído no Windows 8.1, Windows Server 2012 R2, Windows 8, Windows Server 2012, Windows Management Framework 4.0 e Windows Management Framework 3.0. Se esse programa não estiver instalado no computador, os recursos que exigem o WMI, como os comandos CIM, não serão executados.

## <a name="common-language-runtime-40"></a>Common Language Runtime 4.0

O Windows PowerShell 3.0, Windows PowerShell 4.0 e Windows PowerShell 5.0 são compilados no CLR (Common Language Runtime) 4.0.

## <a name="graphical-user-interface-requirements"></a>Requisitos da interface gráfica do usuário

O Windows PowerShell é um aplicativo baseado em console que não exige uma interface gráfica do usuário.
Ele é adequado para computadores que não têm telas, monitores nem uma interface do usuário, como as opções de instalação Server Core do Windows Server 2012 R2 ou do Windows Server 2012.

Alguns itens exigem uma interface gráfica do usuário. Para obter mais detalhes, confira o artigo de ajuda de cada item.

- ISE (Ambiente de Script Integrado) do Windows PowerShell. Para obter mais informações, confira [Apresentamos o ISE do Windows PowerShell](/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).
- Cmdlets
  - [Out-GridView](/powershell/module/microsoft.powershell.utility/out-gridview)
  - [Show-Command](/powershell/module/Microsoft.PowerShell.Utility/Show-Command)
  - [Show-ControlPanelItem](/powershell/module/Microsoft.PowerShell.Management/Show-ControlPanelItem)
  - [Show-EventLog](/powershell/module/Microsoft.PowerShell.Management/Show-EventLog)
- Parâmetros
  - Parâmetro **ShowWindow** do cmdlet [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help).
  - Parâmetro **ShowSecurityDescriptorUI** dos cmdlets [Register-PSSessionConfiguration](/powershell/module/Microsoft.PowerShell.Core/Register-PSSessionConfiguration) e [Set-PSSessionConfiguration](/powershell/module/Microsoft.PowerShell.Core/Set-PSSessionConfiguration).

## <a name="windows-powershell-engine-requirements"></a>Requisitos do mecanismo do Windows PowerShell

O Windows PowerShell 4.0 é projetado para ser compatível com o PowerShell 3.0 e o Windows PowerShell 2.0. Cmdlets, provedores, snap-ins, módulos e scripts escritos para o Windows PowerShell 2.0 e Windows PowerShell 3.0 são executados sem alteração no Windows PowerShell 4.0.

No entanto, devido a uma alteração na política de ativação de runtime no Microsoft .NET Framework 4, os programas host do Windows PowerShell escritos para o Windows PowerShell 2.0 e compilados com o CLR (Common Language Runtime) 2.0 não podem ser executados sem modificações no Windows PowerShell 3.0, que é compilado com o CLR 4.0.

O requisito mínimo do mecanismo do Windows PowerShell 2.0 é o Microsoft .NET Framework 2.0.50727. Esse requisito é atendido pelo Microsoft .NET Framework 3.5 Service Pack 1. Esse requisito não é atendido pelo Microsoft .NET Framework 4 e pelas versões posteriores do Microsoft .NET Framework.

Para obter informações sobre como adicionar ou instalar o mecanismo do Windows PowerShell 2.0 e adicionar ou instalar as versões necessárias do Microsoft .NET Framework, consulte [Installing the Windows PowerShell 2.0 Engine](Installing-the-Windows-PowerShell-2.0-Engine.md) (Instalando o mecanismo do Windows PowerShell 2.0). Para obter informações sobre como iniciar o mecanismo do Windows PowerShell 2.0, consulte [Iniciando o Mecanismo do Windows PowerShell 2.0](../Starting-the-Windows-PowerShell-2.0-Engine.md).

## <a name="windows-preinstallation-environment"></a>Ambiente de Pré-instalação do Windows

O Windows PowerShell 2.0, o Windows PowerShell 3.0 e o Windows PowerShell 4.0 são executados no Windows PE (Ambiente de Pré-Instalação do Windows). No entanto, não há suporte para os cmdlets a seguir.

- Cmdlets do BITS (Serviço de Transferência Inteligente em Segundo Plano). Para obter mais informações, confira [BitsTransfer](/powershell/module/bitstransfer/).
- [Get-EventLog](/powershell/module/Microsoft.PowerShell.Management/Get-EventLog)
- [Get-WinEvent](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent)
- [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help)
- [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)

O serviço **WinRM** não está presente no Windows PE.

## <a name="see-also"></a>Confira também

[Instalar o Windows PowerShell](Installing-Windows-PowerShell.md)

[Iniciando o Windows PowerShell](../Starting-Windows-PowerShell.md)

[Windows Management Framework](../wmf/overview.md)
