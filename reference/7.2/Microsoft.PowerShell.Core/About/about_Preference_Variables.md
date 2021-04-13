---
description: Variáveis que personalizam o comportamento do PowerShell.
Locale: en-US
ms.date: 04/12/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_preference_variables?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Preference_Variables
ms.openlocfilehash: ffd640f7eac8b27cabce345f11da728945043e46
ms.sourcegitcommit: 74270273e9097352dab174c08123b82063225e2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "107297190"
---
# <a name="about-preference-variables"></a>Sobre variáveis de preferência

## <a name="short-description"></a>Descrição breve

Variáveis que personalizam o comportamento do PowerShell.

## <a name="long-description"></a>Descrição longa

O PowerShell inclui um conjunto de variáveis que permitem que você personalize seu comportamento. Essas variáveis de preferência funcionam como as opções em sistemas baseados em GUI.

As variáveis de preferência afetam o ambiente operacional do PowerShell e todos os comandos executados no ambiente. Em muitos casos, os cmdlets têm parâmetros que você pode usar para substituir o comportamento de preferência para um comando específico.

A tabela a seguir lista as variáveis de preferência e seus valores padrão.

|             Variável             |       Valor Padrão       |
| -------------------------------- | ------------------------- |
| `$ConfirmPreference`             | Alto                      |
| `$DebugPreference`               | SilentlyContinue          |
| `$ErrorActionPreference`         | Continue                  |
| `$ErrorView`                     | ConciseView               |
| `$FormatEnumerationLimit`        | 4                         |
| `$InformationPreference`         | SilentlyContinue          |
| `$LogCommandHealthEvent`         | False (não registrado)        |
| `$LogCommandLifecycleEvent`      | False (não registrado)        |
| `$LogEngineHealthEvent`          | Verdadeiro (registrado)             |
| `$LogEngineLifecycleEvent`       | Verdadeiro (registrado)             |
| `$LogProviderLifecycleEvent`     | Verdadeiro (registrado)             |
| `$LogProviderHealthEvent`        | Verdadeiro (registrado)             |
| `$MaximumHistoryCount`           | 4096                      |
| `$OFS`                           | (Caractere de espaço ( `" "` )) |
| `$OutputEncoding`                | Objeto UTF8Encoding       |
| `$ProgressPreference`            | Continuar                  |
| `$PSDefaultParameterValues`      | (Nenhum-tabela de hash vazia) |
| `$PSEmailServer`                 | (Nenhuma)                    |
| `$PSModuleAutoLoadingPreference` | Tudo                       |
| `$PSSessionApplicationName`      | wsman                     |
| `$PSSessionConfigurationName`    | `http://schemas.microsoft.com/powershell/Microsoft.PowerShell` |
| `$PSSessionOption`               | Consulte [$PSSessionOption](#pssessionoption) |
| `$Transcript`                    | (nenhum)                    |
| `$VerbosePreference`             | SilentlyContinue          |
| `$WarningPreference`             | Continue                  |
| `$WhatIfPreference`              | Falso                     |

O PowerShell inclui as seguintes variáveis de ambiente que armazenam as preferências do usuário. Para obter mais informações sobre essas variáveis de ambiente, consulte [about_Environment_Variables](about_Environment_Variables.md).

- `env:PSExecutionPolicyPreference`
- `$env:PSModulePath`

> [!NOTE]
> As alterações na variável de preferência só entram em vigor em scripts e funções se esses scripts ou funções estiverem definidos no mesmo escopo que o escopo no qual a preferência foi usada. Para obter mais informações, consulte [about_Scopes](about_Scopes.md).

## <a name="working-with-preference-variables"></a>Trabalhando com variáveis de preferência

Este documento descreve cada uma das variáveis de preferência.

Para exibir o valor atual de uma variável de preferência específica, digite o nome da variável. Por exemplo, o comando a seguir exibe o `$ConfirmPreference` valor da variável.

```powershell
 $ConfirmPreference
```

```Output
High
```

Para alterar o valor de uma variável, use uma instrução de atribuição. Por exemplo, a instrução a seguir altera o `$ConfirmPreference` valor do parâmetro para **médio**.

```powershell
$ConfirmPreference = "Medium"
```

Os valores que você define são específicos para a sessão atual do PowerShell. Para tornar as variáveis efetivas em todas as sessões do PowerShell, adicione-as ao seu perfil do PowerShell. Para obter mais informações, consulte [about_Profiles](about_Profiles.md).

## <a name="working-remotely"></a>Trabalhando remotamente

Quando você executa comandos em um computador remoto, os comandos remotos só estão sujeitos às preferências definidas no cliente PowerShell do computador remoto. Por exemplo, quando você executa um comando remoto, o valor da variável do computador remoto `$DebugPreference` determina como o PowerShell responde às mensagens de depuração.

Para obter mais informações sobre comandos remotos, consulte [about_Remote](about_Remote.md).

### <a name="confirmpreference"></a>\$ConfirmPreference

Determina se o PowerShell solicita automaticamente a confirmação antes de executar um cmdlet ou uma função.

Os `$ConfirmPreference` valores válidos da variável são **High**, **Medium** ou **Low**. Os cmdlets e funções são atribuídos a um risco de **alta**, **média** ou **baixa**. Quando o valor da `$ConfirmPreference` variável for menor ou igual ao risco atribuído a um cmdlet ou função, o PowerShell solicitará automaticamente a confirmação antes de executar o cmdlet ou a função.

Se o valor da `$ConfirmPreference` variável for **None**, o PowerShell nunca o solicitará automaticamente antes de executar um cmdlet ou uma função.

Para alterar o comportamento de confirmação de todos os cmdlets e funções na sessão, altere o `$ConfirmPreference` valor da variável.

Para substituir o `$ConfirmPreference` para um único comando, use o parâmetro **Confirm** de um cmdlet ou de uma função. Para solicitar confirmação, use `-Confirm` . Para suprimir a confirmação, use `-Confirm:$false` .

Valores válidos de `$ConfirmPreference` :

- **Nenhum**: o PowerShell não é solicitado automaticamente. Para solicitar a confirmação de um comando específico, use o parâmetro **Confirm** do cmdlet ou da função.
- **Baixo**: o PowerShell solicita confirmação antes de executar cmdlets ou funções com um risco baixo, médio ou alto.
- **Médio**: o PowerShell solicita confirmação antes de executar cmdlets ou funções com um médio ou alto risco.
- **Alta**: o PowerShell solicita confirmação antes de executar cmdlets ou funções com um risco alto.

#### <a name="detailed-explanation"></a>Explicação detalhada

O PowerShell pode solicitar automaticamente a confirmação antes de realizar uma ação. Por exemplo, quando o cmdlet ou a função afeta significativamente o sistema para excluir dados ou usar uma quantidade significativa de recursos do sistema.

```powershell
Remove-Item -Path C:\file.txt
```

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target "C:\file.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"):
```

A estimativa do risco é um atributo do cmdlet ou da função conhecida como seu **ConfirmImpact**. Os usuários não podem alterá-la.

Os cmdlets e funções que podem representar um risco para o sistema têm um parâmetro **Confirm** que você pode usar para solicitar ou suprimir a confirmação de um único comando.

Como a maioria dos cmdlets e funções usa o valor de risco padrão, **ConfirmImpact**, de **Medium** e o valor padrão de `$ConfirmPreference` é **alta**, a confirmação automática raramente ocorre. No entanto, você pode ativar a confirmação automática alterando o valor de `$ConfirmPreference` para **médio** ou **baixo**.

#### <a name="examples"></a>Exemplos

Este exemplo mostra o efeito do `$ConfirmPreference` valor padrão da variável, **alto**. O valor **alto** só confirma cmdlets e funções de alto risco. Como a maioria dos cmdlets e funções são de risco médio, eles não são automaticamente confirmados e `Remove-Item` excluem o arquivo. Adicionar `-Confirm` ao comando solicita ao usuário a confirmação.

```powershell
$ConfirmPreference
```

```Output
High
```

```powershell
Remove-Item -Path C:\temp1.txt
```

Use `-Confirm` para solicitar confirmação.

```powershell
Remove-Item -Path C:\temp2.txt -Confirm
```

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target "C:\temp2.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All
[?] Help (default is "Y"):
```

O exemplo a seguir mostra o efeito de alterar o valor de `$ConfirmPreference` para **médio**. Como a maioria dos cmdlets e funções são de risco médio, elas são automaticamente confirmadas. Para suprimir o prompt de confirmação de um único comando, use o parâmetro **Confirm** com um valor de `$false` .

```powershell
$ConfirmPreference = "Medium"
Remove-Item -Path C:\temp2.txt
```

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target "C:\temp2.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All
[?] Help (default is "Y"):
```

```powershell
Remove-Item -Path C:\temp3.txt -Confirm:$false
```

### <a name="debugpreference"></a>\$DebugPreference

Determina como o PowerShell responde a mensagens de depuração geradas por um script, um cmdlet ou um provedor ou por um `Write-Debug` comando na linha de comando.

Alguns cmdlets exibem mensagens de depuração, que normalmente são mensagens técnicas projetadas para programadores e profissionais de suporte técnico. Por padrão, as mensagens de depuração não são exibidas, mas você pode exibir mensagens de depuração alterando o valor de `$DebugPreference` .

Você pode usar o parâmetro comum de **depuração** de um cmdlet para exibir ou ocultar as mensagens de depuração para um comando específico. Para obter mais informações, confira [about_CommonParameters](about_CommonParameters.md).

Os valores válidos são os seguintes:

- **Parar**: exibe a mensagem de depuração e para a execução. Grava um erro no console.
- **Consultar**: exibe a mensagem de depuração e pergunta se você deseja continuar. Adicionar o parâmetro de **depuração** comum a um comando, quando o comando é configurado para gerar uma mensagem de depuração, altera o valor da `$DebugPreference` variável para **consulta**.
- **Continuar**: exibe a mensagem de depuração e continua com a execução.
- **SilentlyContinue**: (padrão) sem efeito. A mensagem de depuração não é exibida e a execução continua sem interrupção.

#### <a name="examples"></a>Exemplos

Os exemplos a seguir mostram o efeito de alterar os valores de `$DebugPreference` quando um `Write-Debug` comando é inserido na linha de comando.
A alteração afeta todas as mensagens de depuração, incluindo as mensagens geradas por cmdlets e scripts. Os exemplos mostram o parâmetro **debug** , que exibe ou oculta as mensagens de depuração relacionadas a um único comando.

Este exemplo mostra o efeito do `$DebugPreference` valor padrão da variável, **SilentlyContinue**. Por padrão, a `Write-Debug` mensagem de depuração do cmdlet não é exibida e o processamento continua. Quando o parâmetro de **depuração** é usado, ele substitui a preferência por um único comando. A mensagem de depuração é exibida.

```powershell
$DebugPreference
```

```Output
SilentlyContinue
```

```powershell
Write-Debug -Message "Hello, World"
```

```powershell
Write-Debug -Message "Hello, World" -Debug
```

```Output
DEBUG: Hello, World
```

Este exemplo mostra o efeito de `$DebugPreference` com o valor de **continue** . A mensagem de depuração é exibida e o comando continua a processar.

```powershell
$DebugPreference = "Continue"
Write-Debug -Message "Hello, World"
```

```Output
DEBUG: Hello, World
```

Este exemplo usa o parâmetro **debug** com um valor de `$false` para suprimir a mensagem para um único comando. A mensagem de depuração não é exibida.

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

Este exemplo mostra o efeito de `$DebugPreference` ser definido como o valor de **parada** . A mensagem de depuração é exibida e o comando é interrompido.

```powershell
$DebugPreference = "Stop"
Write-Debug -Message "Hello, World"
```

```Output
DEBUG: Hello, World
Write-Debug : The running command stopped because the preference variable
 "DebugPreference" or common parameter is set to Stop: Hello, World
At line:1 char:1
+ Write-Debug -Message "Hello, World"
```

Este exemplo usa o parâmetro **debug** com um valor de `$false` para suprimir a mensagem para um único comando. A mensagem de depuração não é exibida e o processamento não é interrompido.

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

Este exemplo mostra o efeito de `$DebugPreference` ser definido como o valor de **consulta** . A mensagem de depuração é exibida e a confirmação do usuário é solicitada.

```powershell
$DebugPreference = "Inquire"
Write-Debug -Message "Hello, World"
```

```Output
DEBUG: Hello, World

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
```

Este exemplo usa o parâmetro **debug** com um valor de `$false` para suprimir a mensagem para um único comando. A mensagem de depuração não é exibida e o processamento continua.

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

### <a name="erroractionpreference"></a>\$ErrorActionPreference

Determina como o PowerShell responde a um erro de não encerramento, um erro que não interrompe o processamento do cmdlet. Por exemplo, na linha de comando ou em um script, cmdlet ou provedor, como os erros gerados pelo `Write-Error` cmdlet.

Você pode usar um parâmetro comum **ErrorAction** de um cmdlet para substituir a preferência para um comando específico.

Os valores válidos são os seguintes:

- **Quebra** – Insira o depurador quando ocorrer um erro ou quando uma exceção for gerada.
- **Continuar**: (padrão) exibe a mensagem de erro e continua em execução.
- **Ignorar**: suprime a mensagem de erro e continua a executar o comando. O valor de **ignorar** destina-se ao uso por comando, não para uso como preferência salva. **Ignore** não é um valor válido para a `$ErrorActionPreference` variável.
- **Consultar**: exibe a mensagem de erro e pergunta se você deseja continuar.
- **SilentlyContinue**: nenhum efeito. A mensagem de erro não é exibida e a execução continua sem interrupção.
- **Parar**: exibe a mensagem de erro e para a execução. Além do erro gerado, o valor de **parada** gera um objeto ActionPreferenceStopException para o fluxo de erro.
  fluxo
- **Suspender**: suspende automaticamente uma tarefa de fluxo de trabalho para permitir uma investigação adicional. Após a investigação, o fluxo de trabalho pode ser retomado. O valor de **suspensão** destina-se ao uso por comando, não para uso como preferência salva. **Suspend** não é um valor válido para a `$ErrorActionPreference` variável.

`$ErrorActionPreference` e o parâmetro **ErrorAction** não afeta como o PowerShell responde a erros de encerramento que param o processamento do cmdlet. Para obter mais informações sobre o parâmetro comum **ErrorAction** , consulte [about_CommonParameters](about_CommonParameters.md).

#### <a name="examples"></a>Exemplos

Esses exemplos mostram o efeito dos diferentes valores da `$ErrorActionPreference` variável. O parâmetro **ErrorAction** é usado para substituir o `$ErrorActionPreference` valor.

Este exemplo mostra o `$ErrorActionPreference` valor padrão, **continue**. Um erro de não finalização é gerado. A mensagem é exibida e o processamento continua.

```powershell
# Change the ErrorActionPreference to 'Continue'
$ErrorActionPreference = 'Continue'
# Generate a non-terminating error and continue processing the script.
Write-Error -Message  'Test Error' ; Write-Host 'Hello World'
```

```Output
Write-Error: Test Error
Hello World
```

Este exemplo mostra o `$ErrorActionPreference` valor padrão, **inquire**. Um erro é gerado e um prompt de ação é mostrado.

```powershell
# Change the ErrorActionPreference to 'Inquire'
$ErrorActionPreference = 'Inquire'
Write-Error -Message 'Test Error' ; Write-Host 'Hello World'
```

```Output
Confirm
Test Error
[Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend  [?] Help (default is "Y"):
```

Este exemplo mostra o `$ErrorActionPreference` conjunto como **SilentlyContinue**.
A mensagem de erro é suprimida.

```powershell
# Change the ErrorActionPreference to 'SilentlyContinue'
$ErrorActionPreference = 'SilentlyContinue'
# Generate an error message
Write-Error -Message 'Test Error' ; Write-Host 'Hello World'
# Error message is suppressed and script continues processing
```

```Output
Hello World
```

Este exemplo mostra o `$ErrorActionPreference` conjunto a ser **interrompido**. Ele também mostra o objeto extra gerado para a `$Error` variável.

```powershell
# Change the ErrorActionPreference to 'Stop'
$ErrorActionPreference = 'Stop'
# Error message is is generated and script stops processing
Write-Error -Message 'Test Error' ; Write-Host 'Hello World'

# Show the ActionPreferenceStopException and the error generated
$Error[0]
$Error[1]
```

```Output
Write-Error: Test Error

ErrorRecord                 : Test Error
WasThrownFromThrowStatement : False
TargetSite                  : System.Collections.ObjectModel.Collection`1[System.Management.Automation.PSObject]
                              Invoke(System.Collections.IEnumerable)
StackTrace                  :    at System.Management.Automation.Runspaces.PipelineBase.Invoke(IEnumerable input)
                                 at Microsoft.PowerShell.Executor.ExecuteCommandHelper(Pipeline tempPipeline,
                              Exception& exceptionThrown, ExecutionOptions options)
Message                     : The running command stopped because the preference variable "ErrorActionPreference" or
                              common parameter is set to Stop: Test Error
Data                        : {System.Management.Automation.Interpreter.InterpretedFrameInfo}
InnerException              :
HelpLink                    :
Source                      : System.Management.Automation
HResult                     : -2146233087

Write-Error: Test Error
```

### <a name="errorview"></a>\$ErrorView

Determina o formato de exibição das mensagens de erro no PowerShell.

Os valores válidos são os seguintes:

- **ConciseView**: (padrão) fornece uma mensagem de erro concisa e uma exibição Refatorada para construtores de módulo avançados. A partir do PowerShell 7,2, se o erro for da linha de comando ou de um módulo de script, a saída será uma mensagem de erro de linha única. Caso contrário, você receberá uma mensagem de erro de várias linhas que contém o erro e um ponteiro para o erro mostrando onde ele ocorre nessa linha. Se o terminal der suporte ao terminal virtual, os códigos de cor ANSI serão usados para fornecer acentos de cor. A cor de destaque pode ser alterada em `$Host.PrivateData.ErrorAccentColor` . Use `Get-Error` o cmdlet para uma exibição detalhada abrangente do erro totalmente qualificado, incluindo as exceções internas.

  **ConciseView** foi adicionado no PowerShell 7.

- **NormalView**: uma exibição detalhada projetada para a maioria dos usuários. Consiste em uma descrição do erro e no nome do objeto envolvido no erro.

- **CategoryView**: um modo de exibição sucinta e estruturado projetado para ambientes de produção. O formato é o seguinte:

  {Category}: ({TargetName}: {TargetType}): [{atividade}], {Reason}

Para obter mais informações sobre os campos em **CategoryView**, consulte classe [ErrorCategoryInfo](/dotnet/api/system.management.automation.errorcategoryinfo) .

#### <a name="examples"></a>Exemplos

Este exemplo mostra como um erro aparece quando o valor de `$ErrorView` é o padrão, **ConciseView**. `Get-ChildItem` é usado para localizar um diretório não existente.

```powershell
Get-ChildItem -path 'C:\NoRealDirectory'
```

```Output
Get-ChildItem: Cannot find path 'C:\NoRealDirectory' because it does not exist.
```

Este exemplo mostra como um erro aparece quando o valor de `$ErrorView` é o padrão, **ConciseView**. `Script.ps1` é executado e gera um erro da `Get-Item` instrução.

```powershell
./Script.ps1
```

```Output
Get-Item: C:\Script.ps1
Line |
  11 | Get-Item -Path .\stuff
     | ^ Cannot find path 'C:\demo\stuff' because it does not exist.
```

Este exemplo mostra como um erro aparece quando o valor de `$ErrorView` é alterado para **NormalView**. `Get-ChildItem` é usado para localizar um arquivo não existente.

```powershell
Get-ChildItem -Path C:\nofile.txt
```

```Output
Get-ChildItem : Cannot find path 'C:\nofile.txt' because it does not exist.
At line:1 char:1
+ Get-ChildItem -Path C:\nofile.txt
```

Este exemplo mostra como o mesmo erro aparece quando o valor de `$ErrorView` é alterado para **CategoryView**.

```powershell
$ErrorView = "CategoryView"
Get-ChildItem -Path C:\nofile.txt
```

```Output
ObjectNotFound: (C:\nofile.txt:String) [Get-ChildItem], ItemNotFoundException
```

Este exemplo demonstra que o valor de `$ErrorView` afeta apenas a exibição do erro. Ele não altera a estrutura do objeto de erro que está armazenado na `$Error` variável automática. Para obter informações sobre a `$Error` variável automática, consulte [about_Automatic_Variables](about_Automatic_Variables.md).

O comando a seguir usa o objeto **ErrorRecord** associado ao erro mais recente na matriz de erros, o **elemento 0**, e formata todas as propriedades do objeto de erro em uma lista.

```powershell
$Error[0] | Format-List -Property * -Force
```

```Output
PSMessageDetails      :
Exception             : System.Management.Automation.ItemNotFoundException:
                          Cannot find path 'C:\nofile.txt' because it does
                          not exist.
                        at System.Management.Automation.SessionStateInternal.
                          GetChildItems(String path, Boolean recurse, UInt32
                          depth, CmdletProviderContext context)
                        at System.Management.Automation.ChildItemCmdlet
                          ProviderIntrinsics.Get(String path, Boolean
                          recurse, UInt32 depth, CmdletProviderContext context)
                        at Microsoft.PowerShell.Commands.GetChildItemCommand.
                          ProcessRecord()
TargetObject          : C:\nofile.txt
CategoryInfo          : ObjectNotFound: (C:\nofile.txt:String) [Get-ChildItem],
                          ItemNotFoundException
FullyQualifiedErrorId : PathNotFound,
                          Microsoft.PowerShell.Commands.GetChildItemCommand
ErrorDetails          :
InvocationInfo        : System.Management.Automation.InvocationInfo
ScriptStackTrace      : at <ScriptBlock>, <No file>: line 1
PipelineIterationInfo : {0, 1}
```

### <a name="formatenumerationlimit"></a>\$FormatEnumerationLimit

Determina quantos itens enumerados são incluídos em uma exibição. Essa variável não afeta os objetos subjacentes, apenas a exibição. Quando o valor de `$FormatEnumerationLimit` for menor que o número de itens enumerados, o PowerShell adicionará reticências ( `...` ) para indicar itens não mostrados.

**Valores válidos**: inteiros ( `Int32` )

**Valor padrão**: 4

#### <a name="examples"></a>Exemplos

Este exemplo mostra como usar a `$FormatEnumerationLimit` variável para melhorar a exibição de itens enumerados.

O comando neste exemplo gera uma tabela que lista todos os serviços em execução no computador em dois grupos: um para a **execução** de serviços e outro para serviços **interrompidos** . Ele usa um `Get-Service` comando para obter todos os serviços e, em seguida, envia os resultados por meio do pipeline para o `Group-Object` cmdlet, que agrupa os resultados pelo status do serviço.

O resultado é uma tabela que lista o status na coluna **nome** e os processos na coluna **grupo** . Para alterar os rótulos de coluna, use uma tabela de hash, consulte [about_Hash_Tables](about_Hash_Tables.md). Para obter mais informações, consulte os exemplos em [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).

Localize o valor atual de `$FormatEnumerationLimit` .

```powershell
$FormatEnumerationLimit
```

```Output
4
```

Lista todos os serviços agrupados por **status**. Há um máximo de quatro serviços listados na coluna **grupo** para cada status, pois `$FormatEnumerationLimit` o tem um valor de **4**.

```powershell
Get-Service | Group-Object -Property Status
```

```Output
Count  Name       Group
-----  ----       -----
60     Running    {AdtAgent, ALG, Ati HotKey Poller, AudioSrv...}
41     Stopped    {Alerter, AppMgmt, aspnet_state, ATI Smart...}
```

Para aumentar o número de itens listados, aumente o valor de `$FormatEnumerationLimit` para **1000**. Use `Get-Service` e `Group-Object` para exibir os serviços.

```powershell
$FormatEnumerationLimit = 1000
Get-Service | Group-Object -Property Status
```

```Output
Count  Name       Group
-----  ----       -----
60     Running    {AdtAgent, ALG, Ati HotKey Poller, AudioSrv, BITS, CcmExec...
41     Stopped    {Alerter, AppMgmt, aspnet_state, ATI Smart, Browser, CiSvc...
```

Use `Format-Table` com o parâmetro **Wrap** para exibir a lista de serviços.

```powershell
Get-Service | Group-Object -Property Status | Format-Table -Wrap
```

```Output
Count  Name       Group
-----  ----       -----
60     Running    {AdtAgent, ALG, Ati HotKey Poller, AudioSrv, BITS, CcmExec,
                  Client for NFS, CryptSvc, DcomLaunch, Dhcp, dmserver,
                  Dnscache, ERSvc, Eventlog, EventSystem, FwcAgent, helpsvc,
                  HidServ, IISADMIN, InoRPC, InoRT, InoTask, lanmanserver,
                  lanmanworkstation, LmHosts, MDM, Netlogon, Netman, Nla,
                  NtLmSsp, PlugPlay, PolicyAgent, ProtectedStorage, RasMan,
                  RemoteRegistry, RpcSs, SamSs, Schedule, seclogon, SENS,
                  SharedAccess, ShellHWDetection, SMT PSVC, Spooler,
                  srservice, SSDPSRV, stisvc, TapiSrv, TermService, Themes,
                  TrkWks, UMWdf, W32Time, W3SVC, WebClient, winmgmt, wscsvc,
                  wuauserv, WZCSVC, zzInterix}

41     Stopped    {Alerter, AppMgmt, aspnet_state, ATI Smart, Browser, CiSvc,
                  ClipSrv, clr_optimization_v2.0.50727_32, COMSysApp,
                  CronService, dmadmin, FastUserSwitchingCompatibility,
                  HTTPFilter, ImapiService, Mapsvc, Messenger, mnmsrvc,
                  MSDTC, MSIServer, msvsmon80, NetDDE, NetDDEdsdm, NtmsSvc,
                  NVSvc, ose, RasAuto, RDSessMgr, RemoteAccess, RpcLocator,
                  SCardSvr, SwPrv, SysmonLog, TlntSvr, upnphost, UPS, VSS,
                  WmdmPmSN, Wmi, WmiApSrv, xmlprov}
```

### <a name="informationpreference"></a>\$InformationPreference

A `$InformationPreference` variável permite definir as preferências de fluxo de informações que você deseja exibir aos usuários. Especificamente, as mensagens informativas que você adicionou a comandos ou scripts adicionando o cmdlet [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information) . Se o parâmetro **informationaction** for usado, seu valor substituirá o valor da `$InformationPreference` variável. `Write-Information` foi introduzido no PowerShell 5,0.

Os valores válidos são os seguintes:

- **Stop**: interrompe um comando ou script em uma ocorrência do `Write-Information` comando.
- **Consultar**: exibe a mensagem informativa que você especifica em um `Write-Information` comando e pergunta se deseja continuar.
- **Continuar**: exibe a mensagem informativa e continua em execução.
- A **suspensão** está disponível somente para fluxos de trabalho que não têm suporte no PowerShell 6 e posteriores.
- **SilentlyContinue**: (padrão) sem efeito. As mensagens informativas não são exibidas e o script continua sem interrupção.

### <a name="logevent"></a>\$Evento log *

As variáveis de preferência de **evento log *** determinam quais tipos de eventos são gravados no log de eventos do PowerShell em Visualizador de eventos. Por padrão, somente os eventos de mecanismo e provedor são registrados em log. Mas, você pode usar as variáveis de preferência de **evento log *** para personalizar o log, como registrar eventos sobre comandos.

As variáveis de preferência de **evento log *** são as seguintes:

- `$LogCommandHealthEvent`: Registra erros e exceções na inicialização e no processamento do comando. O padrão é `$false` (não registrado).
- `$LogCommandLifecycleEvent`: Registra o início e a interrupção de comandos e pipelines de comando e exceções de segurança na descoberta de comando. O padrão é `$false` (não registrado).
- `$LogEngineHealthEvent`: Registra erros e falhas de sessões. O padrão é `$true` (registrado).
- `$LogEngineLifecycleEvent`: Registra a abertura e o fechamento de sessões. O padrão é `$true` (registrado).
- `$LogProviderHealthEvent`: Registra erros do provedor, como erros de leitura e gravação, erros de pesquisa e erros de invocação. O padrão é `$true` (registrado).
- `$LogProviderLifecycleEvent`: Logs adicionando e removendo provedores do PowerShell. O padrão é `$true` (registrado). Para obter informações sobre provedores do PowerShell, consulte [about_Providers](about_Providers.md).

Para habilitar um **evento log ***, digite a variável com um valor de `$true` , por exemplo:

```powershell
$LogCommandLifeCycleEvent = $true
```

Para desabilitar um tipo de evento, digite a variável com um valor de `$false` , por exemplo:

```powershell
$LogCommandLifeCycleEvent = $false
```

Os eventos que você habilita são efetivos apenas para o console atual do PowerShell. Para aplicar a configuração a todos os consoles, salve as configurações de variável em seu perfil do PowerShell. Para obter mais informações, consulte [about_Profiles](about_Profiles.md).

### <a name="maximumhistorycount"></a>\$MaximumHistoryCount

Determina quantos comandos são salvos no histórico de comandos para a sessão atual.

**Valores válidos**: 1-32768 ( `Int32` )

**Padrão**: 4096

Para determinar o número de comandos salvos no momento no histórico de comandos, digite:

```powershell
(Get-History).Count
```

Para ver os comandos salvos em seu histórico de sessão, use o `Get-History` cmdlet. Para obter mais informações, consulte [about_History](about_History.md).

### <a name="ofs"></a>\$OFS

O separador de campo de saída (OFS) especifica o caractere que separa os elementos de uma matriz que é convertida em uma cadeia de caracteres.

**Valores válidos**: qualquer cadeia de caracteres.

**Padrão**: espaço

Por padrão, a `$OFS` variável não existe e o separador de arquivo de saída é um espaço, mas você pode adicionar essa variável e defini-la como qualquer cadeia de caracteres. Você pode alterar o valor de `$OFS` em sua sessão, digitando `$OFS="<value>"` .

> [!NOTE]
> Se você estiver esperando o valor padrão de um espaço ( `" "` ) em seu script, módulo ou saída de configuração, tenha cuidado para que o `$OFS` valor padrão não tenha sido alterado em outro lugar em seu código.

#### <a name="examples"></a>Exemplos

Este exemplo mostra que um espaço é usado para separar os valores quando uma matriz é convertida em uma cadeia de caracteres. Nesse caso, uma matriz de inteiros é armazenada em uma variável e, em seguida, a variável é convertida como uma cadeia de caracteres.

```powershell
$array = 1,2,3,4
[string]$array
```

```Output
1 2 3 4
```

Para alterar o separador, adicione a `$OFS` variável atribuindo um valor a ela.
A variável deve ser nomeada `$OFS` .

```powershell
$OFS = "+"
[string]$array
```

```Output
1+2+3+4
```

Para restaurar o comportamento padrão, você pode atribuir um espaço ( `" "` ) ao valor `$OFS` ou excluir a variável. Os comandos a seguir excluem a variável e, em seguida, verificam se o separador é um espaço.

```powershell
Remove-Variable OFS
[string]$array
```

```Output
1 2 3 4
```

### <a name="outputencoding"></a>\$OutputEncoding

Determina o método de codificação de caracteres que o PowerShell usa quando envia texto para outros aplicativos.

Por exemplo, se um aplicativo retornar cadeias de caracteres Unicode para o PowerShell, talvez seja necessário alterar o valor para **UnicodeEncoding** para enviar os caracteres corretamente.

Os valores válidos são os seguintes: objetos derivados de uma classe de codificação, como **ASCIIEncoding**, **SBCSCodePageEncoding**, **UTF7Encoding**, **UTF8Encoding**, **UTF32Encoding** e **UnicodeEncoding**.

**Padrão**: objeto UTF8Encoding (System. Text. UTF8Encoding)

#### <a name="examples"></a>Exemplos

Este exemplo mostra como fazer com que o comando **findstr.exe** do Windows funcione no PowerShell em um computador localizado para um idioma que usa caracteres Unicode, como o chinês.

O primeiro comando localiza o valor de `$OutputEncoding` . Como o valor é um objeto de codificação, exiba somente sua propriedade **EncodingName** .

```powershell
$OutputEncoding.EncodingName
```

Neste exemplo, um comando **findstr.exe** é usado para pesquisar dois caracteres chineses que estão presentes no `Test.txt` arquivo. Quando esse comando de **findstr.exe** é executado no prompt de comando do Windows (**cmd.exe**), **findstr.exe** localiza os caracteres no arquivo de texto. No entanto, quando você executa o mesmo comando **findstr.exe** no PowerShell, os caracteres não são encontrados porque o PowerShell os envia para **findstr.exe** em texto ASCII, em vez de em texto Unicode.

```powershell
findstr <Unicode-characters>
```

Para fazer com que o comando funcione no PowerShell, defina o valor de `$OutputEncoding` para o valor da propriedade **OutputEncoding** do console do, que se baseia na localidade selecionada para Windows. Como **OutputEncoding** é uma propriedade estática do console, use dois-pontos duplos ( `::` ) no comando.

```powershell
$OutputEncoding = [console]::OutputEncoding
$OutputEncoding.EncodingName
```

```Output
OEM United States
```

Após a alteração da codificação, o comando **findstr.exe** localiza os caracteres Unicode.

```powershell
findstr <Unicode-characters>
```

```Output
test.txt:         <Unicode-characters>
```

### <a name="progresspreference"></a>\$ProgressPreference

Determina como o PowerShell responde a atualizações de progresso geradas por um script, um cmdlet ou um provedor, como as barras de progresso geradas pelo cmdlet [Write-Progress](xref:Microsoft.PowerShell.Utility.Write-Progress) .
O `Write-Progress` cmdlet cria barras de progresso que mostram o status de um comando.

Os valores válidos são os seguintes:

- **Parar**: não exibe a barra de progresso. Em vez disso, ele exibe uma mensagem de erro e para de executar.
- **Consultar**: não exibe a barra de progresso. Solicita permissão para continuar. Se você responder com `Y` ou `A` , ele exibirá a barra de progresso.
- **Continuar**: (padrão) exibe a barra de progresso e continua com a execução.
- **SilentlyContinue**: executa o comando, mas não exibe a barra de progresso.

### <a name="psemailserver"></a>\$PSEmailServer

Especifica o servidor de email padrão que é usado para enviar mensagens de email. Essa variável de preferência é usada por cmdlets que enviam email, como o cmdlet [Send-MailMessage](xref:Microsoft.PowerShell.Utility.Send-MailMessage) .

### <a name="psdefaultparametervalues"></a>\$PSDefaultParameterValues

Especifica valores padrão para os parâmetros de cmdlets e funções avançadas.
O valor de `$PSDefaultParameterValues` é uma tabela de hash em que a chave consiste no nome do cmdlet e no nome do parâmetro separados por dois-pontos ( `:` ). O valor é um valor padrão personalizado que você especifica.

`$PSDefaultParameterValues` foi introduzido no PowerShell 3,0.

Para obter mais informações sobre essa variável de preferência, consulte [about_Parameters_Default_Values](about_Parameters_Default_Values.md).

### <a name="psmoduleautoloadingpreference"></a>\$PSModuleAutoloadingPreference

Habilita e desabilita a importação automática de módulos na sessão. **All** é o padrão. Independentemente do valor da variável, você pode usar [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module) para importar um módulo.

Os valores válidos são:

- **Todos: os** módulos são importados automaticamente no primeiro uso. Para importar um módulo, obtenha ou use qualquer comando no módulo. Por exemplo, use `Get-Command`.
- **ModuleQualified**: os módulos são importados automaticamente somente quando um usuário usa o nome qualificado por módulo de um comando no módulo. Por exemplo, se o usuário digitar `MyModule\MyCommand` , o PowerShell importará o módulo **MyModule** .
- **Nenhum**: a importação automática de módulos está desabilitada na sessão. Para importar um módulo, use o `Import-Module` cmdlet.

Para obter mais informações sobre a importação automática de módulos, consulte [about_Modules](about_Modules.md).

### <a name="pssessionapplicationname"></a>\$PSSessionApplicationName

Especifica o nome do aplicativo padrão para um comando remoto que usa a tecnologia de serviços da Web para gerenciamento (WS-Management). Para obter mais informações, consulte [About gerenciamento remoto do Windows](/windows/win32/winrm/about-windows-remote-management).

O nome do aplicativo padrão do sistema é `WSMAN` , mas você pode usar essa variável de preferência para alterar o padrão.

O nome do aplicativo é o último nó em um URI de conexão. Por exemplo, o nome do aplicativo no exemplo de URI a seguir é `WSMAN` .

`http://Server01:8080/WSMAN`

O nome do aplicativo padrão é usado quando o comando remoto não especifica um URI de conexão ou um nome de aplicativo.

O serviço **WinRM** usa o nome do aplicativo para selecionar um ouvinte para atender à solicitação de conexão. O valor do parâmetro deve corresponder ao valor da propriedade **URLPrefix** de um ouvinte no computador remoto.

Para substituir o padrão do sistema e o valor dessa variável e selecionar um nome de aplicativo diferente para uma sessão específica, use os parâmetros **conexãouri** ou **ApplicationName** dos cmdlets [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)ou [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command) .

A `$PSSessionApplicationName` variável de preferência é definida no computador local, mas especifica um ouvinte no computador remoto. Se o nome do aplicativo especificado não existir no computador remoto, o comando para estabelecer a sessão falhará.

### <a name="pssessionconfigurationname"></a>\$PSSessionConfigurationName

Especifica a configuração de sessão padrão usada para **PSSessions** criadas na sessão atual.

Essa variável de preferência é definida no computador local, mas especifica uma configuração de sessão que está localizada no computador remoto.

O valor da `$PSSessionConfigurationName` variável é um URI de recurso totalmente qualificado.

O valor padrão `http://schemas.microsoft.com/PowerShell/microsoft.PowerShell` indica a configuração de sessão do **Microsoft. PowerShell** no computador remoto.

Se você especificar apenas um nome de configuração, o seguinte URI de esquema será anexado:

`http://schemas.microsoft.com/PowerShell/`

Você pode substituir o padrão e selecionar uma configuração de sessão diferente para uma sessão específica usando o parâmetro **ConfigurationName** dos `New-PSSession` `Enter-PSSession` `Invoke-Command` cmdlets, ou.

Você pode alterar o valor dessa variável a qualquer momento. Quando você fizer isso, lembre-se de que a configuração de sessão selecionada deve existir no computador remoto. Caso contrário, o comando para criar uma sessão que usa a configuração de sessão falhará.

Essa variável de preferência não determina quais configurações de sessão local são usadas quando usuários remotos criam uma sessão que se conecta a este computador.
No entanto, você pode usar as permissões para as configurações de sessão local para determinar quais usuários podem usá-las.

### <a name="pssessionoption"></a>\$PSSessionOption

Estabelece os valores padrão para opções de usuário avançadas em uma sessão remota.
Essas preferências de opção substituem os valores padrão do sistema para as opções de sessão.

A `$PSSessionOption` variável contém um objeto **PSSessionOption** . Para obter mais informações, consulte [System. Management. Automation. Remoting. PSSessionOption](/dotnet/api/system.management.automation.remoting.pssessionoption).
Cada propriedade do objeto representa uma opção de sessão. Por exemplo, a propriedade **NoCompression** desativa a compactação de dados durante a sessão.

Por padrão, a `$PSSessionOption` variável contém um objeto **PSSessionOption** com os valores padrão para todas as opções, como mostrado abaixo.

```Output
MaximumConnectionRedirectionCount : 5
NoCompression                     : False
NoMachineProfile                  : False
ProxyAccessType                   : None
ProxyAuthentication               : Negotiate
ProxyCredential                   :
SkipCACheck                       : False
SkipCNCheck                       : False
SkipRevocationCheck               : False
OperationTimeout                  : 00:03:00
NoEncryption                      : False
UseUTF16                          : False
IncludePortInSPN                  : False
OutputBufferingMode               : None
Culture                           :
UICulture                         :
MaximumReceivedDataSizePerCommand :
MaximumReceivedObjectSize         : 209715200
ApplicationArguments              :
OpenTimeout                       : 00:03:00
CancelTimeout                     : 00:01:00
IdleTimeout                       : -00:00:00.0010000
```

Para obter descrições dessas opções e mais informações, consulte [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption). Para obter mais informações sobre comandos e sessões remotas, consulte [about_Remote](about_Remote.md) e [about_PSSessions](about_PSSessions.md).

Para alterar o valor da `$PSSessionOption` variável de preferência, use o `New-PSSessionOption` cmdlet para criar um objeto **PSSessionOption** com os valores de opção que você preferir. Salve a saída em uma variável chamada `$PSSessionOption` .

```powershell
$PSSessionOption = New-PSSessionOption -NoCompression
```

Para usar a `$PSSessionOption` variável de preferência em cada sessão do PowerShell, adicione um `New-PSSessionOption` comando que cria a `$PSSessionOption` variável ao seu perfil do PowerShell. Para obter mais informações, consulte [about_Profiles](about_Profiles.md).

Você pode definir opções personalizadas para uma sessão remota específica. As opções definidas têm precedência sobre os padrões do sistema e o valor da variável de `$PSSessionOption` preferência.

Para definir opções de sessão personalizadas, use o `New-PSSessionOption` cmdlet para criar um objeto **PSSessionOption** . Em seguida, use o objeto **PSSessionOption** como o valor do parâmetro **SessionOption** em cmdlets que criam uma sessão, como `New-PSSession` , `Enter-PSSession` e `Invoke-Command` .

### <a name="transcript"></a>$Transcript

Usado pelo `Start-Transcript` para especificar o nome e o local do arquivo de transcrição. Se você não especificar um valor para o parâmetro **path** , o `Start-Transcript` usará o caminho no valor da `$Transcript` variável global. Se você não tiver criado essa variável, `Start-Transcript` o armazenará as transcrições no `$Home\My Documents` diretório como `\PowerShell_transcript.<time-stamp>.txt` arquivos.

### <a name="verbosepreference"></a>\$VerbosePreference

Determina como o PowerShell responde a mensagens detalhadas geradas por um script, um cmdlet ou um provedor, como as mensagens geradas pelo cmdlet [Write-Verbose](xref:Microsoft.PowerShell.Utility.Write-Verbose) .
As mensagens detalhadas descrevem as ações executadas para executar um comando.

Por padrão, as mensagens detalhadas não são exibidas, mas você pode alterar esse comportamento alterando o valor de `$VerbosePreference` .

Você pode usar o parâmetro comum **detalhado** de um cmdlet para exibir ou ocultar as mensagens detalhadas de um comando específico. Para obter mais informações, confira [about_CommonParameters](about_CommonParameters.md).

Os valores válidos são os seguintes:

- **Parar**: exibe a mensagem detalhada e uma mensagem de erro e, em seguida, interrompe a execução.
- **Consultar**: exibe a mensagem detalhada e, em seguida, exibe um prompt que pergunta se você deseja continuar.
- **Continuar**: exibe a mensagem detalhada e continua com a execução.
- **SilentlyContinue**: (padrão) não exibe a mensagem detalhada. Continua em execução.

#### <a name="examples"></a>Exemplos

Esses exemplos mostram o efeito dos diferentes valores de `$VerbosePreference` e o parâmetro **Verbose** para substituir o valor de preferência.

Este exemplo mostra o efeito do valor **SilentlyContinue** , que é o padrão. O comando usa o parâmetro **Message** , mas não grava uma mensagem no console do PowerShell.

```powershell
Write-Verbose -Message "Verbose message test."
```

Quando o parâmetro **Verbose** é usado, a mensagem é gravada.

```powershell
Write-Verbose -Message "Verbose message test." -Verbose
```

```Output
VERBOSE: Verbose message test.
```

Este exemplo mostra o efeito do valor de **continuação** . A `$VerbosePreference` variável é definida como **continuar** e a mensagem é exibida.

```powershell
$VerbosePreference = "Continue"
Write-Verbose -Message "Verbose message test."
```

```Output
VERBOSE: Verbose message test.
```

Este exemplo usa o parâmetro **Verbose** com um valor `$false` que substitui o valor **continue** . A mensagem não é exibida.

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

Este exemplo mostra o efeito do valor de **parada** . A `$VerbosePreference` variável é definida como **parar** e a mensagem é exibida. O comando é interrompido.

```powershell
$VerbosePreference = "Stop"
Write-Verbose -Message "Verbose message test."
```

```Output
VERBOSE: Verbose message test.
Write-Verbose : The running command stopped because the preference variable
  "VerbosePreference" or common parameter is set to Stop: Verbose message test.
At line:1 char:1
+ Write-Verbose -Message "Verbose message test."
```

Este exemplo usa o parâmetro **Verbose** com um valor `$false` que substitui o valor de **parada** . A mensagem não é exibida.

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

Este exemplo mostra o efeito do valor de **consulta** . A `$VerbosePreference` variável é definida como **inquire**. A mensagem é exibida e a confirmação do usuário é solicitada.

```powershell
$VerbosePreference = "Inquire"
Write-Verbose -Message "Verbose message test."
```

```Output
VERBOSE: Verbose message test.

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
```

Este exemplo usa o parâmetro **Verbose** com um valor `$false` que substitui o valor de **consulta** . O usuário não é solicitado e a mensagem não é exibida.

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

### <a name="warningpreference"></a>\$WarningPreference

Determina como o PowerShell responde a mensagens de aviso geradas por um script, um cmdlet ou um provedor, como as mensagens geradas pelo cmdlet [Write-Warning](xref:Microsoft.PowerShell.Utility.Write-Warning) .

Por padrão, as mensagens de aviso são exibidas e a execução continua, mas você pode alterar esse comportamento alterando o valor de `$WarningPreference` .

Você pode usar o parâmetro de **aviso** comum de um cmdlet para determinar como o PowerShell responde a avisos de um comando específico. Para obter mais informações, confira [about_CommonParameters](about_CommonParameters.md).

Os valores válidos são os seguintes:

- **Parar**: exibe a mensagem de aviso e uma mensagem de erro e, em seguida, interrompe a execução.
- **Consultar**: exibe a mensagem de aviso e solicita permissão para continuar.
- **Continuar**: (padrão) exibe a mensagem de aviso e continua em execução.
- **SilentlyContinue**: não exibe a mensagem de aviso. Continua em execução.

#### <a name="examples"></a>Exemplos

Esses exemplos mostram o efeito dos diferentes valores de `$WarningPreference` .
O parâmetro **WarningAction** substitui o valor de preferência.

Este exemplo mostra o efeito do valor padrão, **continue**.

```powershell
$m = "This action can delete data."
Write-Warning -Message $m
```

```Output
WARNING: This action can delete data.
```

Este exemplo usa o parâmetro **WarningAction** com o valor **SilentlyContinue** para suprimir o aviso. A mensagem não é exibida.

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction SilentlyContinue
```

Este exemplo altera a `$WarningPreference` variável para o valor **SilentlyContinue** . A mensagem não é exibida.

```powershell
$WarningPreference = "SilentlyContinue"
$m = "This action can delete data."
Write-Warning -Message $m
```

Este exemplo usa o parâmetro **WarningAction** para parar quando um aviso é gerado.

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction Stop
```

```Output
WARNING: This action can delete data.
Write-Warning : The running command stopped because the preference variable
  "WarningPreference" or common parameter is set to Stop:
    This action can delete data.
At line:1 char:1
+ Write-Warning -Message $m -WarningAction Stop
```

Este exemplo altera a `$WarningPreference` variável para o valor de **consulta** . A confirmação do usuário é solicitada.

```powershell
$WarningPreference = "Inquire"
$m = "This action can delete data."
Write-Warning -Message $m
```

```Output
WARNING: This action can delete data.

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
```

Este exemplo usa o parâmetro **WarningAction** com o valor **SilentlyContinue**. O comando continua a ser executado e nenhuma mensagem é exibida.

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction SilentlyContinue
```

Este exemplo altera o `$WarningPreference` valor para **parar**.

```powershell
$WarningPreference = "Stop"
$m = "This action can delete data."
Write-Warning -Message $m
```

```Output
WARNING: This action can delete data.
Write-Warning : The running command stopped because the preference variable
  "WarningPreference" or common parameter is set to Stop:
    This action can delete data.
At line:1 char:1
+ Write-Warning -Message $m
```

Este exemplo usa o **avisoaction** com o valor de **consulta** . O usuário receberá uma solicitação quando ocorrer um aviso.

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction Inquire
```

```Output
WARNING: This action can delete data.

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
```

### <a name="whatifpreference"></a>\$WhatIfPreference

Determina se o **WhatIf** é habilitado automaticamente para cada comando que dá suporte a ele. Quando o **WhatIf** é habilitado, o cmdlet relata o efeito esperado do comando, mas não executa o comando.

Os valores válidos são os seguintes:

- **False** (**0**, não habilitado): (padrão) **WhatIf** não é habilitado automaticamente. Para habilitá-lo manualmente, use o parâmetro **WhatIf** do cmdlet.
- **True** (**1**, Enabled): **WhatIf** é habilitado automaticamente em qualquer comando que ofereça suporte a ele. Os usuários podem usar o parâmetro **WhatIf** com um valor de **false** para desabilitá-lo manualmente, como `-WhatIf:$false` .

#### <a name="examples"></a>Exemplos

Esses exemplos mostram o efeito dos diferentes valores de `$WhatIfPreference` .
Eles mostram como usar o parâmetro **WhatIf** para substituir o valor de preferência para um comando específico.

Este exemplo mostra o efeito da `$WhatIfPreference` variável definida como o valor padrão, **false**. Use `Get-ChildItem` para verificar se o arquivo existe.
`Remove-Item` exclui o arquivo. Depois que o arquivo for excluído, você poderá verificar a exclusão com `Get-ChildItem` .

```powershell
Get-ChildItem -Path .\test.txt
Remove-Item -Path ./test.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           9/13/2019    10:53             10 test.txt
```

```powershell
Get-ChildItem -Path .\test.txt
```

```Output
Get-ChildItem : Cannot find path 'C:\Test\test.txt' because it does not exist.
At line:1 char:1
+ Get-ChildItem -File test.txt
```

Este exemplo mostra o efeito de usar o parâmetro **WhatIf** quando o valor de `$WhatIfPreference` é **false**.

Verifique se o arquivo existe.

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

Use o parâmetro **WhatIf** para determinar o resultado da tentativa de excluir o arquivo.

```powershell
Remove-Item -Path .\test2.txt -WhatIf
```

```Output
What if: Performing the operation "Remove File" on target "C:\Test\test2.txt".
``````

Verifique se o arquivo não foi excluído.

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

Este exemplo mostra o efeito da `$WhatIfPreference` variável definida como o valor, **true**. Quando você usa `Remove-Item` para excluir um arquivo, o caminho do arquivo é exibido, mas o arquivo não é excluído.

Tentativa de excluir um arquivo. Uma mensagem é exibida sobre o que aconteceria se `Remove-Item` fosse executado, mas o arquivo não é excluído.

```powershell
$WhatIfPreference = "True"
Remove-Item -Path .\test2.txt
```

```Output
What if: Performing the operation "Remove File" on target "C:\Test\test2.txt".
```

Use `Get-ChildItem` para verificar se o arquivo não foi excluído.

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

Este exemplo mostra como excluir um arquivo quando o valor de `$WhatIfPreference` for **true**. Ele usa o parâmetro **WhatIf** com um valor de `$false` . Use `Get-ChildItem` para verificar se o arquivo foi excluído.

```powershell
Remove-Item -Path .\test2.txt -WhatIf:$false
Get-ChildItem -Path .\test2.txt
```

```Output
Get-ChildItem : Cannot find path 'C:\Test\test2.txt' because it does not exist.
At line:1 char:1
+ Get-ChildItem -Path .\test2.txt
```

Veja a seguir exemplos do `Get-Process` cmdlet que não dá suporte a **WhatIf** e `Stop-Process` que oferece suporte a **WhatIf**. O `$WhatIfPreference` valor da variável é **true**.

`Get-Process` Não dá suporte a **WhatIf**. Quando o comando é executado, ele exibe o processo **Winword** .

```powershell
Get-Process -Name Winword
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    130   119.84     173.38       8.39   15024   4 WINWORD
```

`Stop-Process` o oferece suporte a **WhatIf**. O processo de **Winword** não está parado.

```powershell
Stop-Process -Name Winword
```

```Output
What if: Performing the operation "Stop-Process" on target "WINWORD (15024)".
```

Você pode substituir o `Stop-Process` comportamento de **WhatIf** usando o parâmetro **WhatIf** com um valor de `$false` . O processo de **Winword** foi interrompido.

```powershell
Stop-Process -Name Winword -WhatIf:$false
```

Para verificar se o processo de **Winword** foi interrompido, use `Get-Process` .

```powershell
Get-Process -Name Winword
```

```Output
Get-Process : Cannot find a process with the name "Winword".
  Verify the process name and call the cmdlet again.
At line:1 char:1
+ Get-Process -Name Winword
```

## <a name="see-also"></a>Confira também

[about_Automatic_Variables](about_Automatic_Variables.md)

[about_CommonParameters](about_CommonParameters.md)

[about_Environment_Variables](about_Environment_Variables.md)

[about_Profiles](about_Profiles.md)

[about_Remote](about_Remote.md)

[about_Scopes](about_Scopes.md)

[about_Variables](about_Variables.md)

