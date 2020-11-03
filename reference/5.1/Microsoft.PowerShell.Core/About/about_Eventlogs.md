---
description: O Windows PowerShell cria um log de eventos do Windows chamado "Windows PowerShell" para registrar eventos do Windows PowerShell. Você pode exibir esse log em Visualizador de Eventos ou usando cmdlets que obtêm eventos, como o `Get-EventLog` cmdlet. Por padrão, os eventos de mecanismo e provedor do Windows PowerShell são registrados no log de eventos, mas você pode usar as variáveis de preferência do log de eventos para personalizar o log de eventos. Por exemplo, você pode adicionar eventos sobre comandos do Windows PowerShell.
keywords: powershell, cmdlet
Locale: en-US
ms.date: 11/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_eventlogs?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Eventlogs
ms.openlocfilehash: eb92333c6a6e220e287dcbec1441d2d05aa9275b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196211"
---
# <a name="about-eventlogs"></a>Sobre EventLogs

## <a name="short-description"></a>Descrição breve

O Windows PowerShell cria um log de eventos do Windows chamado "Windows PowerShell" para registrar eventos do Windows PowerShell. Você pode exibir esse log em Visualizador de Eventos ou usando cmdlets que obtêm eventos, como o `Get-EventLog` cmdlet. Por padrão, os eventos de mecanismo e provedor do Windows PowerShell são registrados no log de eventos, mas você pode usar as variáveis de preferência do log de eventos para personalizar o log de eventos. Por exemplo, você pode adicionar eventos sobre comandos do Windows PowerShell.

## <a name="long-description"></a>Descrição longa

O log de eventos do Windows PowerShell registra os detalhes das operações do Windows PowerShell, como iniciar e interromper o mecanismo do programa e iniciar e interromper os provedores do Windows PowerShell. Você também pode registrar detalhes sobre os comandos do Windows PowerShell.

O log de eventos do Windows PowerShell está no grupo logs de aplicativos e serviços. O log do Windows PowerShell é um log de eventos clássico que não usa a tecnologia de eventos do Windows. Para exibir o log, use os cmdlets projetados para logs de eventos clássicos, como `Get-EventLog` .

## <a name="viewing-the-windows-powershell-event-log"></a>Exibindo o log de eventos do Windows PowerShell

Você pode exibir o log de eventos do Windows PowerShell em Visualizador de Eventos ou usando `Get-EventLog` os `Get-WmiObject` cmdlets e. Para exibir o conteúdo do log do Windows PowerShell, digite:

```powershell
Get-EventLog -LogName "Windows PowerShell"
```

Para examinar os eventos e suas propriedades, use o `Sort-Object` cmdlet, o `Group-Object` cmdlet e os cmdlets que contêm o `Format` verbo (os `Format` cmdlets).

Por exemplo, para exibir os eventos no log agrupados pela ID do evento, digite:

```powershell
Get-EventLog "Windows PowerShell" | Format-Table -GroupBy EventID
```

Ou, digite:

```powershell
Get-EventLog "Windows PowerShell" |
  Sort-Object EventID |
  Group-Object EventID
```

Para exibir todos os logs de eventos clássicos, digite:

```powershell
Get-EventLog -List
```

Você também pode usar o `Get-WmiObject` cmdlet para usar as classes de instrumentação de gerenciamento do Windows relacionadas a eventos (WMI) para examinar o log de eventos. Por exemplo, para exibir todas as propriedades do arquivo de log de eventos, digite:

```powershell
Get-WmiObject Win32_NTEventlogFile |
  where LogFileName -EQ "Windows PowerShell" |
  Format-List -Property *
```

Para localizar as classes WMI relacionadas a eventos do Win32, digite:

```powershell
Get-WmiObject -List | where Name -Like "win32*event*"
```

Para obter mais informações, digite "Get-Help Get-EventLog" e "Get-Help Get-WmiObject".

## <a name="selecting-events-for-the-windows-powershell-event-log"></a>Selecionando eventos para o log de eventos do Windows PowerShell

Você pode usar as variáveis de preferência do log de eventos para determinar quais eventos são registrados no log de eventos do Windows PowerShell.

Há seis variáveis de preferência de log de eventos; duas variáveis para cada um dos três componentes de log: o mecanismo (o programa Windows PowerShell), os provedores e os comandos. As variáveis LifeCycleEvent registram eventos de início e parada normais. Os eventos de erro de log das variáveis de integridade.

A tabela a seguir lista as variáveis de preferência de log de eventos.

|Variável                  |Descrição                                    |
|--------------------------|-----------------------------------------------|
|$LogEngineLifeCycleEvent  |Registra o início e a parada do PowerShell          |
|$LogEngineHealthEvent     |Registra erros do programa do PowerShell                 |
|$LogProviderLifeCycleEvent|Registra o início e a interrupção dos provedores do PowerShell|
|$LogProviderHealthEvent   |Registra erros do provedor do PowerShell                |
|$LogCommandLifeCycleEvent |Registra o início e a conclusão de comandos   |
|$LogCommandHealthEvent    |Registra erros de comando                            |

(Para obter informações sobre provedores do Windows PowerShell, consulte [about_Providers](about_Providers.md).)

Por padrão, somente os seguintes tipos de evento são habilitados:

* $LogEngineLifeCycleEvent
* $LogEngineHealthEvent
* $LogProviderLifeCycleEvent
* $LogProviderHealthEvent

Para habilitar um tipo de evento, defina a variável de preferência para esse tipo de evento como $true. Por exemplo, para habilitar eventos de ciclo de vida de comando, digite:

```powershell
$LogCommandLifeCycleEvent
```

Ou, digite:

```powershell
$LogCommandLifeCycleEvent = $true
```

Para desabilitar um tipo de evento, defina a variável de preferência para esse tipo de evento como $false. Por exemplo, para desabilitar eventos de ciclo de vida de comando, digite:

```powershell
$LogProviderLifeCycleEvent = $false
```

Você pode desabilitar qualquer evento, exceto os eventos que indicam que o mecanismo do Windows PowerShell e os provedores principais são iniciados. Esses eventos são gerados antes que os perfis do Windows PowerShell sejam executados e antes que o programa host esteja pronto para aceitar comandos.

As configurações de variável se aplicam somente à sessão atual do Windows PowerShell.
Para aplicá-las a todas as sessões do Windows PowerShell, adicione-as ao seu perfil do Windows PowerShell.

## <a name="logging-module-events"></a>Log de eventos do módulo

A partir do Windows PowerShell 3,0, você pode registrar eventos de execução para os cmdlets e funções nos módulos e snap-ins do Windows PowerShell definindo a propriedade LogPipelineExecutionDetails de módulos e snap-ins como TRUE. No Windows PowerShell 2,0, esse recurso está disponível apenas para snap-ins.

Quando o valor da propriedade LogPipelineExecutionDetails é TRUE ( `$true` ), o Windows PowerShell grava os eventos de execução de cmdlet e função na sessão para o log do Windows PowerShell em Visualizador de eventos. A configuração só é eficaz na sessão atual.

Para habilitar o log de eventos de execução de cmdlets e funções em um módulo, use a seguinte sequência de comandos.

```powershell
Import-Module <ModuleName>
$m = Get-Module <ModuleName>
$m.LogPipelineExecutionDetails = $true
```

Para habilitar o log de eventos de execução de cmdlets em um snap-in, use a seguinte sequência de comandos.

```powershell
$m = Get-PSSnapin <SnapInName> [-Registered]
$m.LogPipelineExecutionDetails = $True
```

Para desabilitar o registro em log, use a mesma sequência de comandos para definir o valor da propriedade como FALSE ( `$false` ).

Você também pode usar a configuração de Política de Grupo "ativar registro em log de módulo" para habilitar e desabilitar o módulo e o registro em log do snap-in. O valor da política inclui uma lista de nomes de módulo e snap-in. Há suporte para caracteres curinga.

Quando "ativar o registro em log de módulo" está definido para um módulo, o valor da propriedade LogPipelineExecutionDetails do módulo é TRUE em todas as sessões e não pode ser alterado.

A configuração da política de grupo ativar log de módulo está localizada nos seguintes caminhos de Política de Grupo:

```
Computer Configuration\
  Administrative Templates\
    Windows Components\
     Windows PowerShell

User Configuration\
  Administrative Templates\
    Windows Components\
      Windows PowerShell
```

A política de configuração de usuário tem precedência sobre a política de configuração do computador e ambas as políticas têm preferência sobre o valor da propriedade LogPipelineExecutionDetails de módulos e snap-ins.

Para obter mais informações sobre essa configuração de Política de Grupo, consulte [about_Group_Policy_Settings](about_Group_Policy_Settings.md).

## <a name="security-and-auditing"></a>Segurança e auditoria

O log de eventos do Windows PowerShell foi projetado para indicar a atividade e fornecer detalhes operacionais para solução de problemas.

No entanto, como a maioria dos logs de eventos de aplicativo baseados no Windows, o log de eventos do Windows PowerShell não foi projetado para ser seguro. Ele não deve ser usado para auditar a segurança ou registrar informações confidenciais ou proprietárias.

Os logs de eventos são projetados para serem lidos e compreendidos pelos usuários. Os usuários podem ler e gravar no log. Um usuário mal-intencionado pode ler um log de eventos em um computador local ou remoto, gravar dados falsos e, em seguida, impedir o registro em log de suas atividades.

## <a name="notes"></a>Observações

Os autores de autores de módulo podem adicionar recursos de registro em seus módulos. Para obter mais informações, consulte [escrevendo um módulo do Windows PowerShell](/powershell/scripting/developer/module/writing-a-windows-powershell-module).

## <a name="see-also"></a>Consulte Também

[Get-EventLog](xref:Microsoft.PowerShell.Management.Get-EventLog)

[Get-WmiObject](xref:Microsoft.PowerShell.Management.Get-WmiObject)

[about_Group_Policy_Settings](about_Group_Policy_Settings.md)

[about_Preference_Variables](about_Preference_Variables.md)
