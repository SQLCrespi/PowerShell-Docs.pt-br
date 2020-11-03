---
description: Fornece informações de segundo plano sobre WMI (Instrumentação de Gerenciamento do Windows) e Windows PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wmi_cmdlets?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WMI_Cmdlets
ms.openlocfilehash: c2099c005cedf64e9621d66d6757419320c9b43e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196132"
---
# <a name="about-wmi-cmdlets"></a>Sobre os cmdlets do WMI

## <a name="short-description"></a>DESCRIÇÃO BREVE

Fornece informações de segundo plano sobre WMI (Instrumentação de Gerenciamento do Windows) e Windows PowerShell.

## <a name="long-description"></a>DESCRIÇÃO LONGA

Este tópico fornece informações sobre a tecnologia do WMI, os cmdlets do WMI para Windows PowerShell, comunicação remota baseada em WMI, aceleradores de WMI e solução de problemas de WMI. Este tópico também fornece links para outras informações sobre WMI.

### <a name="about-wmi"></a>SOBRE O WMI

A WMI (Instrumentação de Gerenciamento do Windows) é a implementação do WBEM (Gerenciamento Corporativo Baseado na Web) da Microsoft, que é uma iniciativa de mercado para desenvolver uma tecnologia padrão para acessar informações de gerenciamento em um ambiente corporativo. A WMI usa o padrão de mercado CIM (Modelo de Informação Comum) para representar sistemas, aplicativos, redes, dispositivos e outros componentes gerenciados. O CIM é desenvolvido e mantido pela DMTF (Distributed Management Task Force). Você pode usar o WMI para gerenciar computadores locais e remotos. Por exemplo, você pode usar o WMI para fazer o seguinte:

- Iniciar um processo em um computador remoto.
- Reinicie um computador remotamente.
- Obtenha uma lista dos aplicativos que estão instalados em um computador local ou remoto.
- Consulte os logs de eventos do Windows em um computador local ou remoto.

### <a name="the-wmi-cmdlets-for-windows-powershell"></a>OS CMDLETS DO WMI PARA O WINDOWS POWERSHELL

O Windows PowerShell implementa a funcionalidade do WMI por meio de um conjunto de cmdlets que estão disponíveis no Windows PowerShell por padrão. Você pode usar esses cmdlets para concluir as tarefas de ponta a ponta necessárias para gerenciar computadores locais e remotos.

Os cmdlets do WMI a seguir estão incluídos.

|Cmdlet           |Descrição                                   |
|-----------------|----------------------------------------------|
|Get-WmiObject    |Obtém instâncias de informações ou classes WMI  |
|                 |sobre as classes disponíveis.                  |
|Invoke-WmiMethod |Chama os métodos WMI.                            |
|Register-WmiEvent|Assina um evento WMI.                    |
|Remove-WmiObject |Exclui instâncias e classes do WMI.            |
|Set-WmiInstance  |Cria ou modifica instâncias de classes WMI. |

### <a name="sample-commands"></a>COMANDOS DE EXEMPLO
O comando a seguir exibe as informações do BIOS para o computador local.

```powershell
C:\PS> get-wmiobject win32_bios | format-list *
```

O comando a seguir exibe informações sobre o serviço WinRM para três computadores remotos.

```powershell
$wql = "select * from win32_service where name='WinRM'"
get-wmiobject -query $wql -computername server01, server01, server03
```

O comando mais complexo a seguir sai de todas as instâncias de um programa.

```powershell
C:\PS> notepad.exe
C:\PS> $wql = "select * from win32_process where name='notepad.exe'"
C:\PS> $np = get-wmiobject -query $wql
C:\PS> $np | remove-wmiobject
```

### <a name="wmi-based-remoting"></a>COMUNICAÇÃO REMOTA BASEADA EM WMI

Embora a capacidade de gerenciar um sistema local por meio do WMI seja útil, são recursos de comunicação remota que tornam o WMI uma ferramenta administrativa poderosa. O WMI usa o DCOM (Component Object Model distribuído) da Microsoft para se conectar e gerenciar sistemas. Talvez seja necessário configurar alguns sistemas para permitir conexões DCOM.
As configurações de firewall e as permissões DCOM bloqueadas podem bloquear a capacidade do WMI de gerenciar sistemas remotamente.

### <a name="wmi-type-accelerators"></a>ACELERADORES DE TIPOS DO WMI

O Windows PowerShell inclui aceleradores de tipos do WMI. Esses aceleradores de tipo WMI (atalhos) permitem um acesso mais direto a objetos WMI do que uma abordagem de acelerador sem tipo permitiria.

Os seguintes aceleradores de tipos têm suporte com o WMI:

[WMISEARCHER]-um atalho para pesquisar objetos WMI.

[WMICLASS]-um atalho para acessar as propriedades e os métodos estáticos de uma classe.

[WMI]-um atalho para obter uma única instância de uma classe.

[WMISEARCHER] é um acelerador de tipo para um ManagementObjectSearcher. Ele pode pegar um construtor de cadeia de caracteres para criar um pesquisador que você pode então fazer um GET () em.

Por exemplo:

```powershell
PS> $s = [WmiSearcher]'Select * from Win32_Process where Handlecount > 1000'
PS> $s.Get() |sort handlecount |ft handlecount,__path,name -auto

count  __PATH                                              name
-----  ------                                              ----
1105   \\SERVER01\root\cimv2:Win32_Process.Handle="3724"   PowerShell...
1132   \\SERVER01\root\cimv2:Win32_Process.Handle="1388"   winlogon.exe
1495   \\SERVER01\root\cimv2:Win32_Process.Handle="2852"   iexplore.exe
1699   \\SERVER01\root\cimv2:Win32_Process.Handle="1204"   OUTLOOK.EXE
1719   \\SERVER01\root\cimv2:Win32_Process.Handle="1912"   iexplore.exe
2579   \\SERVER01\root\cimv2:Win32_Process.Handle="1768"   svchost.exe
```

[WMICLASS] é um acelerador de tipo para ManagementClass. Isso tem um construtor de cadeia de caracteres que usa um caminho WMI local ou absoluto para uma classe WMI e retorna um objeto que está associado a essa classe.

Por exemplo:

```powershell
PS> $c = [WMICLASS]"root\cimv2:WIn32_Process"
PS> $c |fl *
Name             : Win32_Process
__GENUS          : 1
__CLASS          : Win32_Process
__SUPERCLASS     : CIM_Process
__DYNASTY        : CIM_ManagedSystemElement
__RELPATH        : Win32_Process
__PROPERTY_COUNT : 45
__DERIVATION     : {CIM_Process, CIM_LogicalElement,
                   CIM_ManagedSystemElement}
__SERVER         : SERVER01
__NAMESPACE      : ROOT\cimv2
__PATH           : \\SERVER01\ROOT\cimv2:Win32_Process
```

[WMI] é um acelerador de tipo para ManagementObject. Isso tem um construtor de cadeia de caracteres que usa um caminho WMI local ou absoluto para uma instância do WMI e retorna um objeto que está associado a essa instância.

Por exemplo:

```powershell
PS> $p = [WMI]'\\SERVER01\root\cimv2:Win32_Process.Handle="1204"'
PS> $p.Name
OUTLOOK.EXE
```

### <a name="wmi-troubleshooting"></a>SOLUÇÃO DE PROBLEMAS DO WMI

Os problemas a seguir são os problemas mais comuns que podem ocorrer quando você tenta se conectar a um computador remoto.

Problema 1: o computador remoto não está online.

Se um computador estiver offline, você não poderá se conectar a ele usando o WMI.
Você pode ver a seguinte mensagem de erro:

```
Remote server machine does not exist or is unavailable
```

Se você receber essa mensagem de erro, verifique se o computador está online. Tente executar o ping no computador remoto.

Problema 2: você não tem direitos de administrador local no computador remoto.

Para usar o WMI remotamente, você deve ter direitos de administrador local no computador remoto. Se você não fizer isso, o acesso a esse computador será negado.

Para verificar a segurança do namespace:

1. Clique em Iniciar, clique com o botão direito do mouse em Meu Computador e clique em gerenciar.
2. Em gerenciamento do computador, expanda Serviços e aplicativos, clique com o botão direito do mouse em controle WMI e clique em Propriedades.
3. Na caixa de diálogo Propriedades do controle WMI, clique na guia segurança.

Problema 3: um firewall está bloqueando o acesso ao computador remoto.

O WMI usa os protocolos DCOM (COM distribuído) e RPC (chamada de procedimento remoto) para atravessar a rede. Por padrão, muitos firewalls bloqueiam o tráfego de DCOM e RPC. Se o firewall estiver bloqueando esses protocolos, a conexão falhará. Por exemplo, o Firewall do Windows no Microsoft Windows XP Service Pack 2 está configurado para bloquear automaticamente todo o tráfego de rede não solicitado, incluindo DCOM e WMI. Em sua configuração padrão, o Firewall do Windows rejeita uma solicitação WMI de entrada e você recebe a seguinte mensagem de erro:

```
Remote server machine does not exist or is unavailable
```

## <a name="see-also"></a>CONSULTE TAMBÉM

[Sobre o WMI](/windows/win32/wmisdk/about-wmi)

[Solução de problemas do WMI](/windows/win32/wmisdk/wmi-troubleshooting)

[Get-WmiObject](xref:Microsoft.PowerShell.Management.Get-WmiObject)

[Invoke-WmiMethod](xref:Microsoft.PowerShell.Management.Invoke-WmiMethod)

[Register-WmiEvent](xref:Microsoft.PowerShell.Management.Register-WmiEvent)

[Remove-WmiObject](xref:Microsoft.PowerShell.Management.Remove-WmiObject)

[Set-WmiInstance](xref:Microsoft.PowerShell.Management.Set-WmiInstance)
