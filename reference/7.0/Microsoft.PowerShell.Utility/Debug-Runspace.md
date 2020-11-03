---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/debug-runspace?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Runspace
ms.openlocfilehash: 1f347afe89ed63d64e8a8156b7259509800d5d24
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192838"
---
# Debug-Runspace

## SINOPSE
Inicia uma sessão de depuração interativa com um runspace.

## SYNTAX

### RunspaceParameterSet (padrão)

```
Debug-Runspace [-Runspace] <Runspace> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### NameParameterSet

```
Debug-Runspace [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### IdParameterSet

```
Debug-Runspace [-Id] <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InstanceIdParameterSet

```
Debug-Runspace [-InstanceId] <Guid> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Debug-Runspace` cmdlet inicia uma sessão de depuração interativa com um runspace ativo local ou remoto. Você pode encontrar um runspace que deseja depurar pela primeira vez `Get-Process` para localizar os processos associados ao PowerShell, depois `Enter-PSHostProcess` com a ID do processo especificada no parâmetro **ID** para anexar ao processo e, em seguida, `Get-Runspace` para listar os Runspaces dentro do processo de host do PowerShell.

Depois de selecionar um runspace para depurar, se o runspace estiver executando um comando ou script no momento, ou se o script tiver sido interrompido em um ponto de interrupção, o PowerShell abrirá uma sessão de depurador remoto para o runspace. Você pode depurar o script de runspace da mesma forma que os scripts de sessão remota são depurados.

Você só poderá anexar a um processo de host do PowerShell se você for um administrador no computador que está executando o processo ou se você estiver executando o script que deseja depurar. Além disso, você não pode inserir o processo de host que está executando a sessão atual do PowerShell. Você só pode inserir um processo de host que esteja executando uma sessão do PowerShell diferente.

## EXEMPLOS

### Exemplo 1: Depurar um runspace remoto

```
PS C:\> Get-Process -ComputerName "WS10TestServer" -Name "*powershell*"

Handles      WS(K)   VM(M)      CPU(s)    Id  ProcessName
-------      -----   -----      ------    --  -----------
    377      69912     63     2.09      2420  powershell
    399     123396    829     4.48      1152  powershell_ise

PS C:\> Enter-PSSession -ComputerName "WS10TestServer"
[WS10TestServer]:PS C:\> Enter-PSHostProcess -Id 1152
[WS10TestServer:][Process:1152]: PS C:\Users\Test\Documents> Get-Runspace

Id Name            ComputerName    Type          State         Availability
-- ----            ------------    ----          -----         ------------
 1 Runspace1       WS10TestServer  Remote        Opened        Available
 2 RemoteHost      WS10TestServer  Remote        Opened        Busy

PS C:\> [WS10TestServer][Process:1152]: PS C:\Users\Test\Documents> Debug-Runspace -Id 2

Hit Line breakpoint on 'C:\TestWFVar1.ps1:83'
At C:\TestWFVar1.ps1:83 char:1
+ $scriptVar = "Script Variable"
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
[Process:1152]: [RSDBG: 2]: PS C:\> >
```

Neste exemplo, você depura um runspace que está aberto em um computador remoto, WS10TestServer. Na primeira linha do comando, você executa `Get-Process` o no computador remoto e filtra os processos de host do Windows PowerShell. Neste exemplo, você deseja depurar a ID de processo 1152, o processo de host ISE do Windows PowerShell.

No segundo comando, você executa `Enter-PSSession` para abrir uma sessão remota no WS10TestServer. No terceiro comando, você anexa o processo de host ISE do Windows PowerShell em execução no servidor remoto executando `Enter-PSHostProcess` e especificando a ID do processo de host que você obteve no primeiro comando, 1152.

No quarto comando, você lista os Runspaces disponíveis para a ID de processo 1152 executando `Get-Runspace` .
Você anota o número de ID do runspace ocupado; Ele está executando um script que você deseja depurar.

No último comando, você começa a depurar um runspace aberto que está executando um script, TestWFVar1.ps1, executando `Debug-Runspace` e identificando o runspace por sua ID, 2, adicionando o parâmetro **ID** . Como há um ponto de interrupção no script, o depurador é aberto.

## PARAMETERS

### -Id

Especifica o número de ID de um runspace. Você pode executar `Get-Runspace` para mostrar IDs de runspace.

```yaml
Type: System.Int32
Parameter Sets: IdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceId

Especifica um runspace por sua ID de instância, um GUID que você pode mostrar executando `Get-Runspace` .

```yaml
Type: System.Guid
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Especifica um runspace por seu nome. Você pode executar `Get-Runspace` para mostrar os nomes de Runspaces.

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Runspace

Especifica um objeto de runspace. A maneira mais simples de fornecer um valor para esse parâmetro é especificar uma variável que contenha os resultados de um comando filtrado `Get-Runspace` .

```yaml
Type: System.Management.Automation.Runspaces.Runspace
Parameter Sets: RunspaceParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Confirm

Solicita sua confirmação antes de executar o cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Mostra o que aconteceria se o cmdlet fosse executado. O cmdlet não é executado.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Management. Automation. Runspaces. runspace

Você pode canalizar os resultados de um `Get-Runspace` comando para **debug-runspace.**

## SAÍDAS

## OBSERVAÇÕES

`Debug-Runspace` funciona em Runspaces que estão no estado aberto. Se um estado de runspace mudar de aberto para outro Estado, esse runspace será removido automaticamente da lista em execução. Um runspace será adicionado à lista em execução somente se ele atender aos critérios a seguir.

- Se for proveniente de Invoke-Command; ou seja, ele tem uma `Invoke-Command` ID de GUID.
- Se estiver vindo de `Debug-Runspace` ; ou seja, ele tem uma `Debug-Runspace` ID de GUID.
- Se ele estiver vindo de um fluxo de trabalho do PowerShell, e sua ID do job de fluxo de trabalhos for a mesma ID do trabalho do depurador ativo atual.

## LINKS RELACIONADOS

[about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md)

[Debug-Job](../Microsoft.PowerShell.Core/Debug-Job.md)

[Get-Runspace](Get-Runspace.md)

[Get-Process](../Microsoft.PowerShell.Management/Get-Process.md)

[Enter-PSHostProcess](../Microsoft.PowerShell.Core/Enter-PSHostProcess.md)

[Enter-PSSession](../Microsoft.PowerShell.Core/Enter-PSSession.md)
