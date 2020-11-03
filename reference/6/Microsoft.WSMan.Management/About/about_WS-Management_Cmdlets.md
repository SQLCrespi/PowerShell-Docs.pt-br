---
description: Fornece uma visão geral do Web Services for Management (WS-Management) como plano de fundo para usar os cmdlets WS-Management no Windows PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/04/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/about/about_ws-management_cmdlets?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WS Management_Cmdlets
ms.openlocfilehash: 8bb63126ae9a3b73e2e09e4c8da8f0aeaffd270c
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93195592"
---
# <a name="about-ws-management-cmdlets"></a>Sobre WS-Management cmdlets

## <a name="short-description"></a>DESCRIÇÃO BREVE

Fornece uma visão geral do Web Services for Management (WS-Management) como plano de fundo para usar os cmdlets WS-Management no Windows PowerShell.

## <a name="long-description"></a>DESCRIÇÃO LONGA

Este tópico fornece uma visão geral do Web Services for Management (WS-Management) como plano de fundo para usar os cmdlets WS-Management no Windows PowerShell. Este tópico também fornece links para mais informações sobre o WS-Management. A implementação de WS-Management da Microsoft também é conhecida como Gerenciamento Remoto do Windows (WinRM).

## <a name="about-ws-management"></a>Sobre WS-Management

Gerenciamento Remoto do Windows é a implementação da Microsoft do protocolo de WS-Management, um protocolo padrão baseado em SOAP, compatível com o firewall, que permite que os sistemas operacionais e de hardware de diferentes fornecedores interoperem. A especificação do protocolo WS-Management fornece uma maneira comum para que os sistemas acessem e troquem informações de gerenciamento em uma infra-estrutura de ti (tecnologia da informação). A WS-Management e a IPMI (interface de gerenciamento de plataforma inteligente), juntamente com o coletor de eventos, são componentes dos recursos de gerenciamento de hardware do Windows.

O protocolo WS-Management é baseado nas especificações de serviço Web padrão a seguir: HTTPS, SOAP sobre HTTP (perfil WS-I), SOAP 1,2, WS-Addressing, WS-Transfer, WS-Enumeration e WS-Eventing.

## <a name="ws-management-and-wmi"></a>WS-Management e WMI

WS-Management pode ser usado para recuperar dados expostos por Instrumentação de Gerenciamento do Windows (WMI). Você pode obter dados do WMI com scripts ou aplicativos que usam a API de script WS-Management ou por meio da ferramenta de linha de comando WinRM. O WS-Management oferece suporte à maioria das classes e operações WMI familiares, incluindo objetos incorporados. WS-Management pode aproveitar o WMI para coletar dados sobre recursos ou para gerenciar recursos em computadores baseados no Windows. Isso significa que você pode obter dados sobre objetos como discos, adaptadores de rede, serviços ou processos em sua empresa por meio do conjunto existente de classes WMI. Você também pode acessar os dados de hardware que estão disponíveis no provedor padrão de IPMI do WMI.

## <a name="ws-management-windows-powershell-provider-wsman"></a>WS-Management o provedor do Windows PowerShell (WSMan)

O provedor WSMan fornece uma exibição hierárquica das definições de configuração do WS-Management disponíveis. O provedor permite explorar e definir as várias opções de configuração de WS-Management.

## <a name="ws-management-configuration"></a>Configuração de WS-Management

Se WS-Management não estiver instalado e configurado, a comunicação remota do Windows PowerShell não estará disponível, os cmdlets WS-Management não serão executados, WS-Management scripts não são executados e o provedor WSMan não pode executar operações de dados. A ferramenta de linha de comando WS-Management, o WinRM e o encaminhamento de eventos também dependem da configuração de WS-Management.

## <a name="ws-management-cmdlets"></a>WS-Management cmdlets

WS-Management funcionalidade é implementada no Windows PowerShell por meio de um módulo que contém um conjunto de cmdlets e o provedor WSMan. Você pode usar esses cmdlets para concluir as tarefas de ponta a ponta necessárias para gerenciar WS-Management configurações em computadores locais e remotos.

Os cmdlets WS-Management a seguir estão disponíveis.

## <a name="connection-cmdlets"></a>Cmdlets de conexão

- Connect-WSMan: conecta o computador local ao serviço de WS-Management (WinRM) em um computador remoto.

- Disconnect-WSMan: desconecta o computador local do serviço WS-Management (WinRM) em um computador remoto.

## <a name="management-data-cmdlets"></a>Management-Data cmdlets

- Get-WSManInstance: exibe informações de gerenciamento para uma instância de recurso especificada por um URI de recurso.

- Invoke-WSManaction: invoca uma ação no objeto de destino que é especificado pelo URI de recurso e pelos seletores.

- New-WSManInstance: cria uma nova instância de recurso de gerenciamento.

- Remove-WSManInstance: exclui uma instância de recurso de gerenciamento.

- Set-WSManInstance: modifica as informações de gerenciamento relacionadas a um recurso.

## <a name="setup-and-configuration-cmdlets"></a>Cmdlets de instalação e configuração

- Set-WSManQuickConfig: configura o computador local para gerenciamento remoto.
  Você pode usar o cmdlet Set-WSManQuickConfig para configurar WS-Management para permitir conexões remotas com o serviço do WS-Management (WinRM). O cmdlet Set-WSManQuickConfig executa as seguintes operações:
  - Ele determina se o serviço do WS-Management (WinRM) está em execução. Se o serviço WinRM não estiver em execução, o cmdlet Set-WSManQuickConfig iniciará o serviço.
  - Ele define o tipo de inicialização do serviço WS-Management (WinRM) como automático.
  - Ele cria um ouvinte que aceita solicitações de qualquer endereço IP. O protocolo de transporte padrão é HTTP.
  - Ele habilita uma exceção de firewall para tráfego de WS-Management.

  Observação: para executar esse cmdlet no Windows Vista, no Windows Server 2008 e em versões posteriores do Windows, você deve iniciar o Windows PowerShell com a opção "executar como administrador".

- Teste-WSMan: verifica se WS-Management está instalado e configurado. O cmdlet Test-WSMan testa se o serviço de WS-Management (WinRM) está em execução e configurado em um computador local ou remoto.

- Disable-WSManCredSSP: desabilita a autenticação CredSSP em um computador cliente.

- Enable-WSManCredSSP: habilita a autenticação CredSSP em um computador cliente.

- Get-WSManCredSSP: Obtém a configuração relacionada a CredSSP para um computador cliente.

## <a name="ws-management-specific-cmdlets"></a>Cmdlets específicos do WS-Management

- New-WSManSessionOption: cria um objeto WSManSessionOption para usar como entrada para um ou mais parâmetros de um cmdlet WS-Management.

## <a name="additional-ws-management-information"></a>Informações adicionais de WS-Management

Para obter mais informações sobre o WS-Management, consulte os tópicos a seguir na biblioteca do MSDN (Microsoft Developer Network).

[Gerenciamento Remoto do Windows](/windows/win32/winrm/portal)

[Sobre Gerenciamento Remoto do Windows](/windows/win32/winrm/about-windows-remote-management)

[Instalação e configuração para Gerenciamento Remoto do Windows](/windows/win32/winrm/installation-and-configuration-for-windows-remote-management)

[Arquitetura de Gerenciamento Remoto do Windows](/windows/win32/winrm/windows-remote-management-architecture)

[Protocolo WS-Management](/windows/win32/winrm/ws-management-protocol)

[Gerenciamento Remoto do Windows e WMI](/windows/win32/winrm/windows-remote-management-and-wmi)

[URIs do Recurso](/windows/win32/winrm/resource-uris)

[Gerenciamento de hardware remoto](/windows/win32/winrm/remote-hardware-management)

[Eventos](/windows/win32/winrm/events)

## <a name="see-also"></a>CONSULTE TAMBÉM

[Connect-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan)

[Disable-WSManCredSSP](xref:Microsoft.WSMan.Management.Disable-WSManCredSSP)

[Disconnect-WSMan](xref:Microsoft.WSMan.Management.Disconnect-WSMan)

[Enable-WSManCredSSP](xref:Microsoft.WSMan.Management.Enable-WSManCredSSP)

[Get-WSManCredSSP](xref:Microsoft.WSMan.Management.Get-WSManCredSSP)

[Get-WSManInstance](xref:Microsoft.WSMan.Management.Get-WSManInstance)

[Invoke-WSManAction](xref:Microsoft.WSMan.Management.Invoke-WSManAction)

[New-WSManInstance](xref:Microsoft.WSMan.Management.New-WSManInstance)

[Remove-WSManInstance](xref:Microsoft.WSMan.Management.Remove-WSManInstance)

[Set-WSManInstance](xref:Microsoft.WSMan.Management.Set-WSManInstance)

[Set-WSManQuickConfig](xref:Microsoft.WSMan.Management.Set-WSManQuickConfig)

[Test-WSMan](xref:Microsoft.WSMan.Management.Test-WSMan)
