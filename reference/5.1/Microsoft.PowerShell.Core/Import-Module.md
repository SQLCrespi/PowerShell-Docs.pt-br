---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 12/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/import-module?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Module
ms.openlocfilehash: 6b87074f6053189b20b5cc0983f978324420c99b
ms.sourcegitcommit: 7b376314e7640c39a53aac9f0db8bb935514a960
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2020
ms.locfileid: "96564383"
---
# Import-Module

## SINOPSE
Adiciona módulos à sessão atual.

## SYNTAX

### Nome (padrão)

```
Import-Module [-Global] [-Prefix <String>] [-Name] <String[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-PassThru]
 [-AsCustomObject] [-MinimumVersion <Version>] [-MaximumVersion <String>]
 [-RequiredVersion <Version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] [<CommonParameters>]
```

### PSSession

```
Import-Module [-Global] [-Prefix <String>] [-Name] <String[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-PassThru]
 [-AsCustomObject] [-MinimumVersion <Version>] [-MaximumVersion <String>]
 [-RequiredVersion <Version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] -PSSession <PSSession> [<CommonParameters>]
```

### CimSession

```
Import-Module [-Global] [-Prefix <String>] [-Name] <String[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-PassThru]
 [-AsCustomObject] [-MinimumVersion <Version>] [-MaximumVersion <String>]
 [-RequiredVersion <Version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] -CimSession <CimSession> [-CimResourceUri <Uri>] [-CimNamespace <String>]
 [<CommonParameters>]
```

### FullyQualifiedName

```
Import-Module [-Global] [-Prefix <String>] [-FullyQualifiedName] <ModuleSpecification[]>
 [-Function <String[]>] [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force]
 [-PassThru] [-AsCustomObject] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] [<CommonParameters>]
```

### FullyQualifiedNameAndPSSession

```
Import-Module [-Global] [-Prefix <String>] [-FullyQualifiedName] <ModuleSpecification[]>
 [-Function <String[]>] [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force]
 [-PassThru] [-AsCustomObject] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] -PSSession <PSSession> [<CommonParameters>]
```

### Assembly

```
Import-Module [-Global] [-Prefix <String>] [-Assembly] <Assembly[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-PassThru]
 [-AsCustomObject] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber] [-Scope <String>]
 [<CommonParameters>]
```

### ModuleInfo

```
Import-Module [-Global] [-Prefix <String>] [-Function <String[]>] [-Cmdlet <String[]>]
 [-Variable <String[]>] [-Alias <String[]>] [-Force] [-PassThru] [-AsCustomObject]
 [-ModuleInfo] <PSModuleInfo[]> [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] [<CommonParameters>]
```

## DESCRIPTION

O `Import-Module` cmdlet adiciona um ou mais módulos à sessão atual. A partir do PowerShell 3,0, os módulos instalados são automaticamente importados para a sessão quando você usa qualquer comando ou provedor no módulo. No entanto, você ainda pode usar o `Import-Module` comando para importar um módulo.
Você pode desabilitar a importação automática de módulos usando a `$PSModuleAutoloadingPreference` variável de preferência. Para obter mais informações sobre a `$PSModuleAutoloadingPreference` variável, consulte [about_Preference_Variables](About/about_Preference_Variables.md).

Um módulo é um pacote que contém membros que podem ser usados no PowerShell. Os membros incluem cmdlets, provedores, scripts, funções, variáveis e outras ferramentas e arquivos. Após um módulo ser importado, você pode usar os membros do módulo em sua sessão. Para obter mais informações sobre módulos, consulte [about_Modules](About/about_Modules.md).

Por padrão, `Import-Module` o importa todos os membros que o módulo exporta, mas você pode usar os parâmetros **alias**, **função**, **cmdlet** e **variável** para restringir quais membros são importados. O parâmetro **NoClobber** impede a `Import-Module` importação de membros que têm os mesmos nomes que os membros na sessão atual.

`Import-Module` importa um módulo somente para a sessão atual. Para importar o módulo para cada nova sessão, adicione um `Import-Module` comando ao seu perfil do PowerShell. Para obter mais informações sobre perfis, consulte [about_Profiles](About/about_Profiles.md).

Você pode gerenciar computadores remotos com Windows que têm a comunicação remota do PowerShell habilitada criando uma **PSSession** no computador remoto. Em seguida, use o parâmetro **PSSession** do `Import-Module` para importar os módulos que estão instalados no computador remoto. Quando você usa os comandos importados na sessão atual, os comandos são executados implicitamente no computador remoto.

A partir do Windows PowerShell 3,0, você pode usar `Import-Module` para importar módulos de modelo CIM (CIM). Módulos CIM definem cmdlets em arquivos CDXML (cmdlet Definition XML). Esse recurso permite que você use cmdlets que são implementados em assemblies de código não gerenciado, como os escritos em C++.

Para computadores remotos que não têm a comunicação remota do PowerShell habilitada, incluindo computadores que não estão executando o sistema operacional Windows, você pode usar o parâmetro **CIMSession** do `Import-Module` para importar módulos CIM do computador remoto. Os comandos importados são executados implicitamente no computador remoto. Um **CIMSession** é uma conexão com instrumentação de gerenciamento do Windows (WMI) no computador remoto.

## EXEMPLOS

### Exemplo 1: importar os membros de um módulo para a sessão atual

Este exemplo importa os membros do módulo **PSDiagnostics** para a sessão atual.

```powershell
Import-Module -Name PSDiagnostics
```

### Exemplo 2: importar todos os módulos especificados pelo caminho do módulo

Este exemplo importa todos os módulos disponíveis no caminho especificado pela `$env:PSModulePath` variável de ambiente para a sessão atual.

```powershell
Get-Module -ListAvailable | Import-Module
```

### Exemplo 3: importar os membros de vários módulos para a sessão atual

Este exemplo importa os membros dos módulos **PSDiagnostics** e **DISM** para a sessão atual.

```powershell
$m = Get-Module -ListAvailable PSDiagnostics, Dism
Import-Module -ModuleInfo $m
```

O `Get-Module` cmdlet obtém os módulos **PSDiagnostics** e **DISM** e salva os objetos na `$m` variável. O parâmetro **listAvailable** é necessário quando você está obtendo módulos que ainda não foram importados para a sessão.

O parâmetro **ModuleInfo** de `Import-Module` é usado para importar os módulos para a sessão atual.

### Exemplo 4: importar todos os módulos especificados por um caminho

Este exemplo usa um caminho explícito para identificar o módulo a ser importado.

```powershell
Import-Module -Name c:\ps-test\modules\test -Verbose
```

```Output
VERBOSE: Loading module from path 'C:\ps-test\modules\Test\Test.psm1'.
VERBOSE: Exporting function 'my-parm'.
VERBOSE: Exporting function 'Get-Parameter'.
VERBOSE: Exporting function 'Get-Specification'.
VERBOSE: Exporting function 'Get-SpecDetails'.
```

O uso do parâmetro **Verbose** faz com que o `Import-Module` relate o progresso à medida que ele carrega o módulo.
Sem o parâmetro **Verbose**, **PassThru** ou **AsCustomObject** , o não `Import-Module` gera nenhuma saída quando importa um módulo.

### Exemplo 5: restringir os membros do módulo importados em uma sessão

Este exemplo mostra como restringir quais membros de módulo são importados para a sessão e o efeito desse comando na sessão. O parâmetro de **função** limita os membros que são importados do módulo. Você também pode usar os parâmetros **alias**, **variável** e **cmdlet** para restringir outros membros que um módulo importa.

O `Get-Module` cmdlet obtém o objeto que representa o módulo **PSDiagnostics** . A propriedade **ExportedCmdlets** lista todos os cmdlets exportados pelo módulo, mesmo que eles não tenham sido importados.

```powershell
Import-Module PSDiagnostics -Function Disable-PSTrace, Enable-PSTrace
(Get-Module PSDiagnostics).ExportedCommands
```

```Output
Key                          Value
---                          -----
Disable-PSTrace              Disable-PSTrace
Disable-PSWSManCombinedTrace Disable-PSWSManCombinedTrace
Disable-WSManTrace           Disable-WSManTrace
Enable-PSTrace               Enable-PSTrace
Enable-PSWSManCombinedTrace  Enable-PSWSManCombinedTrace
Enable-WSManTrace            Enable-WSManTrace
Get-LogProperties            Get-LogProperties
Set-LogProperties            Set-LogProperties
Start-Trace                  Start-Trace
Stop-Trace                   Stop-Trace
```

```powershell
Get-Command -Module PSDiagnostics
```

```Output
CommandType     Name                 Version    Source
-----------     ----                 -------    ------
Function        Disable-PSTrace      6.1.0.0    PSDiagnostics
Function        Enable-PSTrace       6.1.0.0    PSDiagnostics
```

O uso do parâmetro **Module** do `Get-Command` cmdlet mostra os comandos que foram importados do módulo **PSDiagnostics** . Os resultados confirmam que apenas os `Disable-PSTrace` `Enable-PSTrace` cmdlets e foram importados.

### Exemplo 6: importar os membros de um módulo e adicionar um prefixo

Este exemplo importa o módulo **PSDiagnostics** para a sessão atual, adiciona um prefixo aos nomes de membro e, em seguida, exibe os nomes de membro prefixados. O parâmetro **prefix** de `Import-Module` adiciona o prefixo **x** a todos os membros que são importados do módulo. O prefixo se aplica somente aos membros da sessão atual. Ele não altera o módulo. O parâmetro **PassThru** retorna um objeto de módulo que representa o módulo importado.

```powershell
Import-Module PSDiagnostics -Prefix x -PassThru
```

```Output
ModuleType Version    Name               ExportedCommands
---------- -------    ----               ----------------
Script     6.1.0.0    PSDiagnostics      {Disable-xPSTrace, Disable-xPSWSManCombinedTrace, Disable-xW...
```

```powershell
Get-Command -Module PSDiagnostics
```

```Output
CommandType     Name                                   Version    Source
-----------     ----                                   -------    ------
Function        Disable-xPSTrace                       6.1.0.0    PSDiagnostics
Function        Disable-xPSWSManCombinedTrace          6.1.0.0    PSDiagnostics
Function        Disable-xWSManTrace                    6.1.0.0    PSDiagnostics
Function        Enable-xPSTrace                        6.1.0.0    PSDiagnostics
Function        Enable-xPSWSManCombinedTrace           6.1.0.0    PSDiagnostics
Function        Enable-xWSManTrace                     6.1.0.0    PSDiagnostics
Function        Get-xLogProperties                     6.1.0.0    PSDiagnostics
Function        Set-xLogProperties                     6.1.0.0    PSDiagnostics
Function        Start-xTrace                           6.1.0.0    PSDiagnostics
Function        Stop-xTrace                            6.1.0.0    PSDiagnostics
```

`Get-Command` Obtém os membros que foram importados do módulo. A saída mostra que os membros do módulo foram prefixados corretamente.

### Exemplo 7: obter e usar um objeto personalizado

Este exemplo demonstra como obter e usar o objeto personalizado retornado por `Import-Module` .

Objetos personalizados incluem membros sintéticos que representam cada um dos membros de módulos importados. Por exemplo, os cmdlets e funções em um módulo são convertidos para os métodos de script do objeto personalizado.

Os objetos personalizados são úteis no script. Eles também são úteis quando vários objetos importados têm os mesmos nomes. Usar o método de script de um objeto é equivalente a especificar o nome totalmente qualificado de um membro importado, incluindo o nome de seu módulo.

O parâmetro **AsCustomObject** pode ser usado somente ao importar um módulo de script. Use `Get-Module` para determinar qual dos módulos disponíveis é um módulo de script.

```powershell
Get-Module -List | Format-Table -Property Name, ModuleType -AutoSize
```

```Output
Name          ModuleType
----          ----------
Show-Calendar     Script
BitsTransfer    Manifest
PSDiagnostics   Manifest
TestCmdlets       Script
...
```

```powershell
$a = Import-Module -Name Show-Calendar -AsCustomObject -Passthru
$a | Get-Member
```

```Output
    TypeName: System.Management.Automation.PSCustomObject
Name          MemberType   Definition
----          ----------   ----------
Equals        Method       bool Equals(System.Object obj)
GetHashCode   Method       int GetHashCode()
GetType       Method       type GetType()
ToString      Method       string ToString()
Show-Calendar ScriptMethod System.Object Show-Calendar();
```

```powershell
$a."Show-Calendar"()
```

O `Show-Calendar` módulo de script é importado usando o parâmetro **AsCustomObject** para solicitar um objeto personalizado e o parâmetro **PassThru** para retornar o objeto. O objeto personalizado resultante é salvo na `$a` variável.

A `$a` variável é canalizada para o `Get-Member` cmdlet para mostrar as propriedades e os métodos do objeto salvo. A saída mostra um `Show-Calendar` método de script.

Para chamar o `Show-Calendar` método de script, o nome do método deve ser colocado entre aspas porque o nome inclui um hífen.

### Exemplo 8: reimportar um módulo para a mesma sessão

Este exemplo mostra como usar o parâmetro **Force** de `Import-Module` quando você está importando um módulo para a mesma sessão. O parâmetro **Force** remove o módulo carregado e o importa novamente.

```powershell
Import-Module PSDiagnostics
Import-Module PSDiagnostics -Force -Prefix PS
```

O primeiro comando importa o módulo **PSDiagnostics** . O segundo comando importa o módulo novamente, dessa vez usando o parâmetro **Prefix**.

Sem o parâmetro **Force** , a sessão incluiria duas cópias de cada cmdlet **PSDiagnostics** , uma com o nome padrão e outra com o nome prefixado.

### Exemplo 9: executar comandos que foram ocultados por comandos importados

Este exemplo mostra como executar comandos que foram ocultos por comandos importados. O módulo **TestModule** inclui uma função chamada `Get-Date` que retorna o ano e o dia do ano.

```powershell
Get-Date
```

```Output
Thursday, August 15, 2019 2:26:12 PM
```

```powershell
Import-Module TestModule
Get-Date
```

```Output
19227
```

```powershell
Get-Command Get-Date -All | Format-Table -Property CommandType, Name, ModuleName -AutoSize
```

```Output
CommandType     Name         ModuleName
-----------     ----         ----------
Function        Get-Date     TestModule
Cmdlet          Get-Date     Microsoft.PowerShell.Utility
```

```powershell
Microsoft.PowerShell.Utility\Get-Date
```

```Output
Thursday, August 15, 2019 2:28:31 PM
```

O primeiro `Get-Date` cmdlet retorna um objeto **DateTime** com a data atual. Depois de importar o módulo **TestModule** , `Get-Date` retorna o ano e o dia do ano.

Usando o parâmetro **All** de `Get-Command` Mostrar todos os `Get-Date` comandos na sessão. Os resultados mostram que há dois `Get-Date` comandos na sessão, uma função do módulo **TestModule** e um cmdlet do módulo **Microsoft. PowerShell. Utility** .

Como as funções têm precedência sobre os cmdlets, a `Get-Date` função do módulo **TestModule** é executada, em vez do `Get-Date` cmdlet. Para executar a versão original do `Get-Date` , você deve qualificar o nome do comando com o nome do módulo.

Para obter mais informações sobre a precedência de comando no PowerShell, consulte [about_Command_Precedence](about/about_Command_Precedence.md).

### Exemplo 10: importar uma versão mínima de um módulo

Este exemplo importa o módulo **PowerShellGet** . Ele usa o parâmetro **MinimumVersion** de `Import-Module` para importar somente a versão 2.0.0 ou superior do módulo.

```powershell
Import-Module -Name PowerShellGet -MinimumVersion 2.0.0
```

Você também pode usar o parâmetro **RequiredVersion** para importar uma versão específica de um módulo ou usar os parâmetros de **módulo** e **versão** da `#Requires` palavra-chave para exigir uma versão específica de um módulo em um script.

### Exemplo 11: importar usando um nome totalmente qualificado

Este exemplo importa uma versão específica de um módulo usando o FullyQualifiedName.

```powershell
PS> Get-Module -ListAvailable PowerShellGet | Select-Object Name, Version

Name          Version
----          -------
PowerShellGet 2.2.1
PowerShellGet 2.1.3
PowerShellGet 2.1.2
PowerShellGet 1.0.0.1

PS> Import-Module -FullyQualifiedName @{ModuleName = 'PowerShellGet'; ModuleVersion = '2.1.3' }
```

### Exemplo 12: importar usando um caminho totalmente qualificado

Este exemplo importa uma versão específica de um módulo usando o caminho totalmente qualificado.

```powershell
PS> Get-Module -ListAvailable PowerShellGet | Select-Object Path

Path
----
C:\Program Files\PowerShell\Modules\PowerShellGet\2.2.1\PowerShellGet.psd1
C:\program files\powershell\6\Modules\PowerShellGet\PowerShellGet.psd1
C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\2.1.2\PowerShellGet.psd1
C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PowerShellGet.psd1

PS> Import-Module -Name 'C:\Program Files\PowerShell\Modules\PowerShellGet\2.2.1\PowerShellGet.psd1'
```

### Exemplo 13: importar um módulo de um computador remoto

Este exemplo mostra como usar o `Import-Module` cmdlet para importar um módulo de um computador remoto.
Esse comando usa o recurso de comunicação remota implícita do PowerShell.

Quando importa módulos de outra sessão, você pode usar os cmdlets da sessão atual.
No entanto, os comandos que usam os cmdlets são executados na sessão remota.

```powershell
$s = New-PSSession -ComputerName Server01
Get-Module -PSSession $s -ListAvailable -Name NetSecurity
```

```Output
ModuleType Name             ExportedCommands
---------- ----             ----------------
Manifest   NetSecurity      {New-NetIPsecAuthProposal, New-NetIPsecMainModeCryptoProposal, New-Ne...
```

```powershell
Import-Module -PSSession $s -Name NetSecurity
Get-Command -Module NetSecurity -Name Get-*Firewall*
```

```Output
CommandType     Name                                               ModuleName
-----------     ----                                               ----------
Function        Get-NetFirewallAddressFilter                       NetSecurity
Function        Get-NetFirewallApplicationFilter                   NetSecurity
Function        Get-NetFirewallInterfaceFilter                     NetSecurity
Function        Get-NetFirewallInterfaceTypeFilter                 NetSecurity
Function        Get-NetFirewallPortFilter                          NetSecurity
Function        Get-NetFirewallProfile                             NetSecurity
Function        Get-NetFirewallRule                                NetSecurity
Function        Get-NetFirewallSecurityFilter                      NetSecurity
Function        Get-NetFirewallServiceFilter                       NetSecurity
Function        Get-NetFirewallSetting                             NetSecurity
```

```powershell
Get-NetFirewallRule -DisplayName "Windows Remote Management*" |
  Format-Table -Property DisplayName, Name -AutoSize
```

```Output
DisplayName                                              Name
-----------                                              ----
Windows Remote Management (HTTP-In)                      WINRM-HTTP-In-TCP
Windows Remote Management (HTTP-In)                      WINRM-HTTP-In-TCP-PUBLIC
Windows Remote Management - Compatibility Mode (HTTP-In) WINRM-HTTP-Compat-In-TCP
```

`New-PSSession` Cria uma sessão remota (**PSSession**) para o computador Server01. A **PSSession** é salva na `$s` variável.

A execução `Get-Module` com o parâmetro **PSSession** mostra que o módulo **NetSecurity** está instalado e disponível no computador remoto. Esse comando é equivalente a usar o `Invoke-Command` cmdlet para executar o `Get-Module` comando na sessão remota. Por exemplo: (`Invoke-Command $s {Get-Module -ListAvailable -Name NetSecurity`

A execução `Import-Module` com o parâmetro **PSSession** importa o módulo **NetSecurity** do computador remoto para a sessão atual. O `Get-Command` cmdlet é usado para obter comandos que começam com **Get** e incluem o **Firewall** do módulo **NetSecurity** . A saída confirma que o módulo e seus cmdlets foram importados para a sessão atual.

Em seguida, o `Get-NetFirewallRule` cmdlet obtém gerenciamento remoto do Windows regras de firewall no computador Server01. Isso é equivalente a usar o `Invoke-Command` cmdlet para executar `Get-NetFirewallRule` na sessão remota.

### Exemplo 14: gerenciar o armazenamento em um computador remoto sem o sistema operacional Windows

Neste exemplo, o administrador do computador instalou o provedor WMI de descoberta de módulo, que permite que você use comandos CIM projetados para o provedor.

O `New-CimSession` cmdlet cria uma sessão no computador remoto chamado RSDGF03. A sessão se conecta ao serviço WMI no computador remoto. A sessão CIM é salva na `$cs` variável.
`Import-Module` usa o **CimSession** no `$cs` para importar o módulo CIM de **armazenamento** do computador RSDGF03.

O `Get-Command` cmdlet mostra o `Get-Disk` comando no módulo de **armazenamento** . Quando você importa um módulo CIM para a sessão local, o PowerShell converte os arquivos CDXML para cada comando nos scripts do PowerShell, que aparecem como funções na sessão local.

Embora `Get-Disk` o seja digitado na sessão local, o cmdlet é executado implicitamente no computador remoto do qual ele foi importado. O comando retorna objetos do computador remoto para a sessão local.

```powershell
$cs = New-CimSession -ComputerName RSDGF03
Import-Module -CimSession $cs -Name Storage
# Importing a CIM module, converts the CDXML files for each command into PowerShell scripts.
# These appear as functions in the local session.
Get-Command Get-Disk
```

```Output
CommandType     Name                  ModuleName
-----------     ----                  ----------
Function        Get-Disk              Storage
```

```powershell
# Use implicit remoting to query disks on the remote computer from which the module was imported.
Get-Disk
```

```Output
Number Friendly Name           OperationalStatus  Total Size Partition Style
------ -------------           -----------------  ---------- ---------------
0      Virtual HD ATA Device   Online                  40 GB MBR
```

## PARAMETERS

### -Alias

Especifica os aliases que esse cmdlet importa do módulo para a sessão atual. Digite uma lista de aliases separados por vírgulas. Caracteres curinga são permitidos.

Alguns módulos exportam automaticamente aliases selecionados para sua sessão quando você importa o módulo.
Esse parâmetro permite selecionar dentre os aliases exportados.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -ArgumentList

Especifica uma matriz de argumentos ou valores de parâmetro que são passados para um módulo de script durante o `Import-Module` comando. Esse parâmetro é válido somente quando você está importando um módulo de script.

Você também pode se referir ao parâmetro **ArgumentList** por seu alias, **args**. Para obter mais informações sobre o comportamento de **ArgumentList**, consulte [about_Splatting](about/about_Splatting.md#splatting-with-arrays).

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsCustomObject

Indica que esse cmdlet retorna um objeto personalizado com membros que representam os membros do módulo importados. Este parâmetro é válido somente para módulos de script.

Quando você usa o parâmetro **AsCustomObject** , `Import-Module` o importa os membros do módulo para a sessão e, em seguida, retorna um objeto **PSCustomObject** em vez de um objeto **PSModuleInfo** . Você pode salvar o objeto personalizado em uma variável e usar a notação de ponto para invocar os membros.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Assembly

Especifica uma matriz de objetos de assembly. Esse cmdlet importa os cmdlets e provedores implementados nos objetos de assembly especificados. Insira uma variável que contenha objetos de assembly ou um comando que crie objetos de assembly. Você também pode canalizar um objeto de assembly para `Import-Module` .

Quando você usa esse parâmetro, somente os cmdlets e provedores implementados pelos assemblies especificados são importados. Se o módulo contiver outros arquivos, eles não serão importados e você poderá estar faltando membros importantes do módulo. Use esse parâmetro para depurar e testar o módulo, ou quando for instruído a usá-lo pelo autor do módulo.

```yaml
Type: System.Reflection.Assembly[]
Parameter Sets: Assembly
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CimNamespace

Especifica o namespace de um provedor CIM alternativo que expõe módulos CIM. O valor padrão é o namespace do provedor WMI de detecção de módulos.

Use esse parâmetro para importar módulos CIM de computadores e dispositivos que não estão executando um sistema operacional Windows.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.String
Parameter Sets: CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimResourceUri

Especifica um local alternativo para módulos CIM. O valor padrão é o URI de recurso do provedor WMI de descoberta de módulo no computador remoto.

Use esse parâmetro para importar módulos CIM de computadores e dispositivos que não estão executando um sistema operacional Windows.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Uri
Parameter Sets: CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession

Especifica uma sessão CIM no computador remoto. Insira uma variável que contém a sessão CIM ou um comando que obtém a sessão CIM, como um comando [Get-CimSession](../CimCmdlets/Get-CimSession.md) .

`Import-Module` usa a conexão de sessão CIM para importar módulos do computador remoto para a sessão atual. Quando você usa os comandos do módulo importado na sessão atual, os comandos são executados no computador remoto.

Você pode usar esse parâmetro para importar módulos de computadores e dispositivos que não estão executando o sistema operacional Windows e computadores com Windows que têm o PowerShell, mas que não têm a comunicação remota do PowerShell habilitada.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: Microsoft.Management.Infrastructure.CimSession
Parameter Sets: CimSession
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cmdlet

Especifica uma matriz de cmdlets que esse cmdlet importa do módulo para a sessão atual.
Caracteres curinga são permitidos.

Alguns módulos exportam automaticamente cmdlets selecionados para sua sessão quando você importa o módulo.
Esse parâmetro permite selecionar dentre os cmdlets exportados.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -DisableNameChecking

Indica que esse cmdlet suprime a mensagem que avisa quando você importa um cmdlet ou função cujo nome inclui um verbo não aprovado ou um caractere proibido.

Por padrão, quando um módulo que você importa exporta cmdlets ou funções que têm verbos não aprovados em seus nomes, o PowerShell exibe a seguinte mensagem de aviso:

> Aviso: alguns nomes de comando importados incluem verbos não aprovados que podem torná-los menos detectáveis. Use o parâmetro Verbose para obter mais detalhes ou digite Get-Verb para ver a lista de verbos aprovados."

A mensagem é apenas um aviso. O módulo completo ainda é importado, incluindo os comandos não autorizados. Embora a mensagem seja exibida para usuários do módulo, o problema de nomenclatura deve ser corrigido pelo autor do módulo.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Esse parâmetro faz com que um módulo seja carregado ou recarregado acima do atual.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -FullyQualifiedName

Especifica o nome totalmente qualificado do módulo como uma tabela de hash. O valor pode ser uma combinação de cadeias de caracteres e tabelas de hash. A tabela de hash tem as seguintes chaves.

- `ModuleName` - **Necessário** Especifica o nome do módulo.
- `GUID` - **Opcional** Especifica o GUID do módulo.
- Também é **necessário** especificar uma das três chaves abaixo. Essas chaves não podem ser usadas juntas.
  - `ModuleVersion` -Especifica uma versão mínima aceitável do módulo.
  - `RequiredVersion` -Especifica uma versão exata e necessária do módulo.
  - `MaximumVersion` -Especifica a versão máxima aceitável do módulo.

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: FullyQualifiedName, FullyQualifiedNameAndPSSession
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Função

Especifica uma matriz de funções que esse cmdlet importa do módulo para a sessão atual.
Caracteres curinga são permitidos. Alguns módulos exportam automaticamente funções selecionadas para sua sessão quando você importa o módulo. Esse parâmetro permite selecionar dentre as funções exportadas.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Global

Indica que esse cmdlet importa módulos para o estado de sessão global para que fiquem disponíveis para todos os comandos na sessão.

Por padrão, quando `Import-Module` o cmdlet é chamado no prompt de comando, arquivo de script ou scriptblock, todos os comandos são importados para o estado de sessão global.

Quando invocado de outro módulo, `Import-Module` o cmdlet importa os comandos em um módulo, incluindo comandos de módulos aninhados, para o estado de sessão do módulo de chamada.

> [!TIP]
> Você deve evitar `Import-Module` a chamada de dentro de um módulo. Em vez disso, declare o módulo de destino como um módulo aninhado no manifesto do módulo pai. A declaração de módulos aninhados melhora a descoberta de dependências.

O parâmetro **Global** é equivalente ao parâmetro **Scope** com um valor de **Global**.

Para restringir os comandos exportados por um módulo, use um `Export-ModuleMember` comando no módulo de script.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumVersion

Especifica uma versão máxima. Esse cmdlet importa apenas uma versão do módulo que seja menor ou igual ao valor especificado. Se nenhuma versão for qualificada, `Import-Module` o retornará um erro.

```yaml
Type: System.String
Parameter Sets: Name, PSSession, CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumVersion

Especifica uma versão mínima. Esse cmdlet importa apenas uma versão do módulo que seja maior ou igual ao valor especificado. Use o nome de parâmetro **MinimumVersion** ou seu alias, **Version**. Se nenhuma versão for qualificada, `Import-Module` o gerará um erro.

Para especificar uma versão exata, use o parâmetro **RequiredVersion**. Você também pode usar os parâmetros de **módulo** e **versão** da palavra-chave **#Requires** para exigir uma versão específica de um módulo em um script.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Version
Parameter Sets: Name, PSSession, CimSession
Aliases: Version

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ModuleInfo

Especifica uma matriz de objetos de módulo a ser importada. Insira uma variável que contenha os objetos de módulo ou um comando que obtenha os objetos de módulo, como o seguinte comando: `Get-Module -ListAvailable` . Você também pode canalizar objetos de módulo para `Import-Module` .

```yaml
Type: System.Management.Automation.PSModuleInfo[]
Parameter Sets: ModuleInfo
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Especifica os nomes dos módulos a serem importados. Insira o nome do módulo ou o nome de um arquivo no módulo, como um `.psd1` `.psm1` arquivo,, `.dll` ou `.ps1` . Caminhos de arquivo são opcionais. Caracteres curinga não são permitidos. Também é possível canalizar nomes de módulo e nome de filename para `Import-Module` .

Se você omitir um caminho, `Import-Module` o procurará o módulo nos caminhos salvos na `$env:PSModulePath` variável de ambiente.

Especifique somente o nome de módulo sempre que possível. Quando você especifica um nome de arquivo, somente os membros que são implementados nesse arquivo são importados. Se o módulo contiver outros arquivos, eles não serão importados e você poderá estar faltando membros importantes do módulo.

> [!NOTE]
> Embora seja possível importar um arquivo de script ( `.ps1` ) como um módulo, os arquivos de script normalmente não são estruturados como arquivo de módulos de script ( `.psm1` ). A importação de um arquivo de script não garante que ele seja utilizável como um módulo. Para obter mais informações, consulte [about_Modules](about/about_Modules.md).

```yaml
Type: System.String[]
Parameter Sets: Name, PSSession, CimSession
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### -NoClobber

Impede a importação de comandos que têm os mesmos nomes que os comandos existentes na sessão atual. Por padrão, o `Import-Module` importa todos os comandos de módulo exportados.

Comandos que têm os mesmos nomes podem ocultar ou substituir comandos na sessão. Para evitar conflitos de nome de comando em uma sessão, use os parâmetros **Prefix** ou **NoClobber**. Para obter mais informações sobre conflitos de nome e sobre a precedência dos comandos, consulte "Módulos e Conflitos de Nome" em [about_Modules](about/about_Modules.md) e [about_Command_Precedence](about/about_Command_Precedence.md).

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Retorna um objeto que representa o item com o qual você está trabalhando. Por padrão, este cmdlet não gera saída.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Prefixo

Especifica um prefixo que esse cmdlet adiciona aos substantivos nos nomes dos membros de módulo importados.

Use este parâmetro para evitar conflitos de nome que podem ocorrer quando diferentes membros da sessão têm o mesmo nome. Esse parâmetro não altera o módulo e não afeta os arquivos que o módulo importa para seu próprio uso. Eles são conhecidos como módulos aninhados. Esse cmdlet afeta apenas os nomes dos membros na sessão atual.

Por exemplo, se você especificar o prefixo UTC e, em seguida, importar um `Get-Date` cmdlet, o cmdlet será conhecido na sessão como `Get-UTCDate` , e não será confundido com o `Get-Date` cmdlet original.

O valor deste parâmetro tem precedência sobre a propriedade **DefaultCommandPrefix** do módulo, que especifica o prefixo padrão.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PSSession

Especifica uma sessão gerenciada pelo usuário do PowerShell (**PSSession**) da qual este cmdlet importa módulos para a sessão atual. Insira uma variável que contenha uma **PSSession** ou um comando que obtenha uma **PSSession**, como um `Get-PSSession` comando.

Quando importa um módulo de uma sessão diferente para a sessão atual, você pode usar os cmdlets do módulo na sessão atual, assim como você usaria cmdlets de um módulo local. Os comandos que usam os cmdlets remotos são executados na sessão remota, mas os detalhes de comunicação remota são gerenciados em segundo plano pelo PowerShell.

Esse parâmetro usa o recurso de comunicação remota implícita do PowerShell. É equivalente a usar o `Import-PSSession` cmdlet para importar módulos específicos de uma sessão.

`Import-Module` Não é possível importar módulos do PowerShell Core de outra sessão. Os módulos do PowerShell Core têm nomes que começam com Microsoft. PowerShell.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: PSSession, FullyQualifiedNameAndPSSession
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequiredVersion

Especifica uma versão do módulo que este cmdlet importa. Se a versão não estiver instalada, o `Import-Module` gerará um erro.

Por padrão, `Import-Module` o importa o módulo sem verificar o número de versão.

Para especificar uma versão mínima, use o parâmetro **MinimumVersion**. Você também pode usar os parâmetros de **módulo** e **versão** da palavra-chave **#Requires** para exigir uma versão específica de um módulo em um script.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

Scripts que usam **RequiredVersion** para importar módulos que estão incluídos em versões existentes do sistema operacional Windows não são executados automaticamente em versões futuras do sistema operacional Windows. Isso ocorre porque os números de versão do módulo do PowerShell em versões futuras do sistema operacional Windows são maiores do que os números de versão do módulo em versões existentes do sistema operacional Windows.

```yaml
Type: System.Version
Parameter Sets: Name, PSSession, CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Escopo

Especifica um escopo no qual esse cmdlet importa o módulo.

Os valores aceitáveis para esse parâmetro são:

- **Global**. Disponível para todos os comandos da sessão. Equivalente ao parâmetro **Global**.
- **Local**. Disponível somente no escopo atual.

Por padrão, quando `Import-Module` o cmdlet é chamado no prompt de comando, arquivo de script ou scriptblock, todos os comandos são importados para o estado de sessão global. Você pode usar o `-Scope Local` parâmetro para importar o conteúdo do módulo para o escopo do script ou scriptblock.

Quando invocado de outro módulo, `Import-Module` o cmdlet importa os comandos em um módulo, incluindo comandos de módulos aninhados, para o estado de sessão do chamador. Especificar `-Scope Global` ou `-Global` indicar que este cmdlet importa módulos para o estado de sessão global para que fiquem disponíveis para todos os comandos na sessão.

O parâmetro **Global** é equivalente ao parâmetro **Scope** com um valor de **Global**.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Local, Global

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Variable

Especifica uma matriz de variáveis que este cmdlet importa do módulo para a sessão atual.
Insira uma lista de variáveis. Caracteres curinga são permitidos.

Alguns módulos exportam automaticamente variáveis selecionadas para sua sessão quando você importa o módulo.
Esse parâmetro permite selecionar dentre as variáveis exportadas.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### CommonParameters
Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. String, System. Management. Automation. PSModuleInfo, System. Reflection. assembly

É possível canalizar um nome de módulo, objeto de módulo ou objeto de assembly para este cmdlet.

## SAÍDAS

### Nenhum, System. Management. Automation. PSModuleInfo ou System. Management. Automation. PSCustomObject

Por padrão, `Import-Module` o não gera nenhuma saída. Se você especificar o parâmetro **PassThru** , o cmdlet gerará um objeto **System. Management. Automation. PSModuleInfo** que representa o módulo. Se você especificar o parâmetro **AsCustomObject** , ele gerará um objeto **PSCustomObject** .

## OBSERVAÇÕES

- Antes que você possa importar um módulo, o módulo deve estar instalado no computador local. Ou seja, o diretório do módulo deve ser copiado para um diretório acessível ao seu computador local. Para obter mais informações, consulte [about_Modules](About/about_Modules.md).

  Você também pode usar os parâmetros **PSSession** e **CIMSession** para importar módulos que estão instalados em computadores remotos. No entanto, os comandos que usam os cmdlets nesses módulos são executados na sessão remota no computador remoto.

- Se você importar Membros com o mesmo nome e o mesmo tipo em sua sessão, o PowerShell usará o membro importado por último por padrão. Variáveis e aliases são substituídos e os originais não estão acessíveis. As funções, os cmdlets e os provedores são simplesmente sombreados pelos novos membros. Eles podem ser acessados qualificando o nome do comando com o nome de seu snap-in, módulo ou caminho de função.

- Para atualizar os dados de formatação para comandos que foram importados de um módulo, use o `Update-FormatData` cmdlet. `Update-FormatData` também atualiza os dados de formatação para comandos na sessão que foram importados dos módulos. Se o arquivo de formatação de um módulo for alterado, você poderá executar um `Update-FormatData` comando para atualizar os dados de formatação para comandos importados. Você não precisa importar o módulo novamente.

- A partir do Windows PowerShell 3,0, os comandos principais instalados com o PowerShell são empacotados em módulos. No Windows PowerShell 2,0 e em programas de host que criam sessões de estilo mais antigo em versões posteriores do PowerShell, os comandos principais são empacotados em snap-ins (**PSSnapins**). A exceção é **Microsoft. PowerShell. Core**, que sempre é um snap-in. Além disso, as sessões remotas, como as iniciadas pelo `New-PSSession` cmdlet, são sessões de estilo mais antigo que incluem snap-ins de núcleo.

  Para obter informações sobre o método **CreateDefault2** que cria sessões de estilo mais recente com módulos de núcleo, consulte o [método CreateDefault2](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2).

- No Windows PowerShell 2,0, alguns dos valores de Propriedade do objeto de módulo, como os valores de propriedade **ExportedCmdlets** e **NestedModules** , não foram populados até que o módulo tenha sido importado.

- Se você tentar importar um módulo que contém assemblies de modo misto que não são compatíveis com o Windows PowerShell 3.0 +, `Import-Module` o retornará uma mensagem de erro semelhante à seguinte.

  > Import-Module: o assembly de modo misto é compilado em relação à versão ' v 2.0.50727 ' do tempo de execução e não pode ser carregado no tempo de execução 4,0 sem informações de configuração adicionais.

  Esse erro ocorre quando um módulo projetado para o Windows PowerShell 2,0 contém pelo menos um assembly de módulo misto. Um assembly de módulo misto que inclui código gerenciado e não gerenciado, como C++ e C#.

  Para importar um módulo que contém assemblies de modo misto, inicie o Windows PowerShell 2,0 usando o comando a seguir e tente o `Import-Module` comando novamente.

  `PowerShell.exe -Version 2.0`

- Para usar o recurso de sessão CIM, o computador remoto deve ter comunicação remota do WS-Management e a Instrumentação de Gerenciamento do Windows (WMI), que é a implementação da Microsoft do padrão CIM. O computador também deve ter o provedor de Descoberta do Módulo WMI ou um provedor CIM alternativo que tem os mesmos recursos básicos.

  Você pode usar o recurso de sessão CIM em computadores que não estão executando um sistema operacional Windows e em computadores com Windows que têm o PowerShell, mas não têm a comunicação remota do PowerShell habilitada.

  Você também pode usar os parâmetros CIM para obter módulos CIM de computadores que têm a comunicação remota do PowerShell habilitada, incluindo o computador local. Quando você cria uma sessão CIM no computador local, o PowerShell usa DCOM, em vez de WMI, para criar a sessão.

- Por padrão, o `Import-Module` importa módulos no escopo global mesmo quando chamado de um escopo descendente. O escopo de nível superior e todos os escopos descendentes têm acesso aos elementos exportados do módulo.

  Em um escopo descendente, `-Scope Local` o limita a importação para esse escopo e todos os seus escopos descendentes. Os escopos pai não veem os membros importados.

  > [!NOTE]
  > `Get-Module` mostra todos os módulos carregados na sessão atual. Isso inclui módulos carregados localmente em um escopo descendente. Use `Get-Command -Module modulename` para ver quais membros são carregados no escopo atual.

  `Import-Module` Não carrega definições de classe e enumeração no módulo. Use a `using module` instrução no início do script. Isso importa o módulo, incluindo as definições de classe e enumeração. Para obter mais informações, consulte [about_Using](About/about_Using.md).

## LINKS RELACIONADOS

[about_Modules](about/about_Modules.md)

[Export-ModuleMember](Export-ModuleMember.md)

[Get-Module](Get-Module.md)

[New-Module](New-Module.md)

[Remove-Module](Remove-Module.md)
