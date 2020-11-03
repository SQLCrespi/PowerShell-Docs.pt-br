---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 11/04/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pshostprocess?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enter-PSHostProcess
ms.openlocfilehash: dcc0fc0ddb9486d4bf1f24b7366622c011266a04
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194645"
---
# Enter-PSHostProcess

## SINOPSE
Conecta-se a e entra em uma sessão interativa com um processo local.

## SYNTAX

### ProcessIdParameterSet (padrão)

```
Enter-PSHostProcess [-Id] <Int32> [[-AppDomainName] <String>] [<CommonParameters>]
```

### ProcessParameterSet

```
Enter-PSHostProcess [-Process] <Process> [[-AppDomainName] <String>] [<CommonParameters>]
```

### ProcessNameParameterSet

```
Enter-PSHostProcess [-Name] <String> [[-AppDomainName] <String>] [<CommonParameters>]
```

### PSHostProcessInfoParameterSet

```
Enter-PSHostProcess [-HostProcessInfo] <PSHostProcessInfo> [[-AppDomainName] <String>]
 [<CommonParameters>]
```

### PipeNameParameterSet

```
Enter-PSHostProcess -CustomPipeName <String> [<CommonParameters>]
```

## DESCRIPTION

O `Enter-PSHostProcess` cmdlet se conecta e entra em uma sessão interativa com um processo local. A partir do PowerShell 6,2, esse cmdlet tem suporte em plataformas que não são do Windows.

Em vez de criar um novo processo para hospedar o PowerShell e executar uma sessão remota, a sessão remota e interativa é executada em um processo existente que já está executando o PowerShell. Quando você estiver interagindo com uma sessão remota em um processo especificado, poderá enumerar os Runspaces em execução e, em seguida, selecionar um runspace para depurar executando o `Debug-Runspace` ou o `Enable-RunspaceDebug` .

O processo que você deseja inserir deve estar hospedando o PowerShell (System.Management.Automation.dll).
Você deve ser membro do grupo Administradores no computador em que o processo é encontrado ou deve ser o usuário que está executando o script que iniciou o processo.

Depois que você selecionar um runspace para depurar, uma sessão de depuração remota será aberta para o runspace se estiver executando um comando no momento ou for interrompido no depurador. Em seguida, você pode depurar o script do runspace da mesma forma que depuraria outros scripts de sessão remota.

Desanexar de uma sessão de depuração e, em seguida, a sessão interativa com o processo, executando Exit duas vezes ou parar a execução do script executando o comando Quit do depurador existente.

Se você especificar um processo usando o parâmetro **Name** , e houver apenas um processo encontrado com o nome especificado, o processo será inserido. Se mais de um processo com o nome especificado for encontrado, o PowerShell retornará um erro e listará todos os processos encontrados com o nome especificado.

Para dar suporte à anexação a processos em computadores remotos, o `Enter-PSHostProcess` cmdlet é habilitado em um computador remoto especificado, para que você possa anexar a um processo local dentro de uma sessão remota do PowerShell.

## EXEMPLOS

### Exemplo 1: iniciar a depuração de um runspace dentro do processo do ISE do PowerShell

Neste exemplo, você executa `Enter-PSHostProcess` de dentro do console do PowerShell para entrar no processo do ISE do PowerShell. Na sessão interativa resultante, você pode encontrar um runspace que deseja depurar executando `Get-Runspace` e, em seguida, depurar o runspace.

```
PS C:\> Enter-PSHostProcess -Name powershell_ise
[Process:1520]: PS C:\Test\Documents>

Next, get available runspaces within the process you have entered.
PS C:\> [Process:1520]: PS C:\>  Get-Runspace
Id    Name          InstanceId                               State           Availability
--    -------       -----------                              ------          -------------
1     Runspace1     2d91211d-9cce-42f0-ab0e-71ac258b32b5     Opened          Available
2     Runspace2     a3855043-cb16-424a-a616-685360c3763b     Opened          RemoteDebug
3     MyLocalRS     2236dbd8-2105-4dec-a15a-a27d0bfaacb5     Opened          LocalDebug
4     MyRunspace    771356e9-8c44-4b70-9de5-dd17cb41e48e     Opened          Busy
5     Runspace8     3e517382-a97a-49ba-9c3c-fd21f6664288     Broken          None

The runspace objects returned by Get-Runspace also have a NoteProperty called ScriptStackTrace of
the running command stack, if available.Next, debug runspace ID 4, that is running another user's
long-running script. From the list returned from Get-Runspace, note that the runspace state is
Opened, and Availability is Busy, meaning that the runspace is still running the long-running
script.

PS C:\> [Process:1520]: PS C:\>  (Get-Runspace -Id 4).ScriptStackTrace
Command                    Arguments                           Location
-------                    ---------                           --------
MyModuleWorkflowF1         {}                                  TestNoFile3.psm1: line 6
WFTest1                    {}                                  TestNoFile2.ps1: line 14
TestNoFile2.ps1            {}                                  TestNoFile2.ps1: line 22
<ScriptBlock>              {}                                  <No file>

Start an interactive debugging session with this runspace by running the Debug-Runspace cmdlet.

PS C:\> [Process: 1520]: PS C:\>  Debug-Runspace -Id 4
Hit Line breakpoint on 'C:\TestWFVar1.ps1:83'

At C:\TestWFVar1.ps1:83 char:1
+ $scriptVar = "Script Variable"
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

[Process: 1520]: [RSDBG: 4]: PS C:\> >

After you are finished debugging, allow the script to continue running without the debugger attached
by running the exit debugger command. Alternatively, you can quit the debugger with the q or Stop
commands.

PS C:\> [Process:346]: [RSDBG: 3]: PS C:\> > exit
[Process:1520]: PS C:\>

When you are finished working in the process, exit the process by running the Exit-PSHostProcess
cmdlet. This returns you to the PS C:\> prompt.

PS C:\> [Process:1520]: PS C:\>  Exit-PSHostProcess
PS C:\>
```

## PARAMETERS

### -AppDomainname

Especifica um nome de domínio de aplicativo para se conectar a se omitido, usa **defaultappdomain** . Use `Get-PSHostProcessInfo` para exibir os nomes de domínio do aplicativo.

```yaml
Type: System.String
Parameter Sets: ProcessIdParameterSet, ProcessParameterSet, ProcessNameParameterSet, PSHostProcessInfoParameterSet
Aliases:

Required: False
Position: 1
Default value: DefaultAppDomain
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostProcessInfo

Especifica um objeto **PSHostProcessInfo** que pode ser conectado ao PowerShell. Use `Get-PSHostProcessInfo` para obter o objeto.

```yaml
Type: Microsoft.PowerShell.Commands.PSHostProcessInfo
Parameter Sets: PSHostProcessInfoParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Id

Especifica um processo pela ID do processo. Para obter uma ID de processo, execute o `Get-Process` cmdlet.

```yaml
Type: System.Int32
Parameter Sets: ProcessIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Especifica um processo pelo nome do processo. Para obter um nome de processo, execute o `Get-Process` cmdlet. Você também pode obter nomes de processo na caixa de diálogo Propriedades de um processo no Gerenciador de tarefas.

```yaml
Type: System.String
Parameter Sets: ProcessNameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Processo

Especifica um processo pelo objeto de processo. A maneira mais simples de usar esse parâmetro é salvar os resultados de um `Get-Process` comando que retorne o processo que você deseja inserir em uma variável e, em seguida, especificar a variável como o valor desse parâmetro.

```yaml
Type: System.Diagnostics.Process
Parameter Sets: ProcessParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CustomPipeName

Obtém ou define o nome do pipe nomeado personalizado ao qual se conectar. Normalmente, isso é usado em conjunto com o `pwsh -CustomPipeName` .

Esse parâmetro foi introduzido no PowerShell 6,2.

```yaml
Type: System.String
Parameter Sets: PipeNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.Diagnostics.Process

## SAÍDAS

## OBSERVAÇÕES

`Enter-PSHostProcess` Não é possível inserir o processo da sessão do PowerShell na qual você está executando o comando. No entanto, você pode inserir o processo de outra sessão do PowerShell ou uma sessão do ISE do PowerShell em execução ao mesmo tempo que a sessão em que você está executando `Enter-PSHostProcess` .

`Enter-PSHostProcess` pode inserir somente os processos que estão hospedando o PowerShell. Ou seja, eles carregaram o mecanismo do PowerShell.

Para sair de um processo de dentro do processo, digite **Exit** e pressione <kbd>Enter</kbd>.

## LINKS RELACIONADOS

[Exit-PSHostProcess](Exit-PSHostProcess.md)

[Get-PSHostProcessInfo](Get-PSHostProcessInfo.md)
