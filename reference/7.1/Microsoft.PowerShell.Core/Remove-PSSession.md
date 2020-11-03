---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-pssession?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSSession
ms.openlocfilehash: 1b0fbfca365e9cf369decbf4eafc0a8b4e2741bc
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194570"
---
# Remove-PSSession

## SINOPSE
Fecha uma ou mais sessões do PowerShell (PSSessions).

## SYNTAX

### ID (padrão)

```
Remove-PSSession [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Session

```
Remove-PSSession [-Session] <PSSession[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ContainerId

```
Remove-PSSession -ContainerId <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMId

```
Remove-PSSession -VMId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMName

```
Remove-PSSession -VMName <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InstanceId

```
Remove-PSSession -InstanceId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Name

```
Remove-PSSession -Name <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ComputerName

```
Remove-PSSession [-ComputerName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **Remove-PSSession** fecha sessões do PowerShell ( **PSSessions** ) na sessão atual.
Ele interrompe os comandos que estão em execução nas **PSSessions** , encerra a **PSSession** e libera os recursos que a **PSSession** estava usando.
Se a **PSSession** estiver conectada a um computador remoto, esse cmdlet também fechará a conexão entre os computadores locais e remotos.

Para remover uma **PSSession** , insira o *nome* , *ComputerName* , *ID* ou *InstanceId* da sessão.

Se você salvou a *PSSession* em uma variável, o objeto de sessão permanecerá na variável, mas o estado da *PSSession* será fechado.

## EXEMPLOS

### Exemplo 1: remover sessões usando IDs

```powershell
Remove-PSSession -Id 1, 2
```

Esse comando remove as **PSSessions** que têm as IDs 1 e 2.

### Exemplo 2: remover todas as sessões na sessão atual

```powershell
Get-PSSession | Remove-PSSession
Remove-PSSession -Session (Get-PSSession)
$s = Get-PSSession
Remove-PSSession -Session $s
```

Esses comandos removem todas as **PSSessions** na sessão atual.
Embora o formato dos três comandos pareçam diferentes, eles têm o mesmo efeito.

### Exemplo 3: fechar sessões usando nomes

```powershell
$r = Get-PSSession -ComputerName Serv*
$r | Remove-PSSession
```

Esses comandos fecham as **PSSessions** que estão conectadas a computadores que têm nomes que começam com o serv.

### Exemplo 4: fechar sessões conectadas a uma porta

```powershell
Get-PSSession | where {$_.port -eq 90} | Remove-PSSession
```

Esse comando fecha as **PSSessions** que estão conectadas à porta 90.
Você pode usar esse formato de comando para identificar **PSSessions** por propriedades diferentes de *ComputerName* , *Name* , *InstanceId* e *ID* .

### Exemplo 5: fechar uma sessão com base na ID da instância

```powershell
Get-PSSession | Format-Table ComputerName, InstanceID  -AutoSize
```

```Output
ComputerName InstanceId
------------ ----------------
Server01     875d231b-2788-4f36-9f67-2e50d63bb82a
localhost    c065ffa0-02c4-406e-84a3-dacb0d677868
Server02     4699cdbc-61d5-4e0d-b916-84f82ebede1f
Server03     4e5a3245-4c63-43e4-88d0-a7798bfc2414
TX-TEST-01   fc4e9dfa-f246-452d-9fa3-1adbdd64ae85 PS C:\> Remove-PSSession -InstanceID fc4e9dfa-f246-452d-9fa3-1adbdd64ae85
```

Estes comandos mostram como fechar uma **PSSession** com base em sua ID de instância ou **RemoteRunspaceID** .

O primeiro comando usa o cmdlet **Get-PSSession** para obter as **PSSessions** na sessão atual.
Ele usa um operador de pipeline (|) para enviar as **PSSessions** para o cmdlet Format-Table, que formata suas propriedades **ComputerName** e **InstanceId** em uma tabela.
O parâmetro *AutoSize* compacta as colunas para exibição.

Na exibição resultante, você pode identificar a **PSSession** a ser fechada e copiar e colar a *InstanceId* dessa **PSSession** no segundo comando.

O segundo comando usa o cmdlet **Remove-PSSession** para remover a *PSSession* com a ID de instância especificada.

### Exemplo 6: criar uma função que exclui todas as sessões na sessão atual

```powershell
Function EndPSS { Get-PSSession | Remove-PSSession }
```

Essa função exclui todas as **PSSessions** na sessão atual.
Depois de adicionar essa função ao seu perfil do PowerShell, para excluir todas as sessões, digite `EndPSS` .

## PARAMETERS

### -ComputerName

Especifica uma matriz de nomes de computadores.
Esse cmdlet fecha as **PSSessions** que estão conectadas aos computadores especificados.
Caracteres curinga são permitidos.

Digite o nome NetBIOS, um endereço IP ou um nome de domínio totalmente qualificado de um ou mais computadores remotos.
Para especificar o computador local, digite o nome do computador, localhost ou um ponto (.).

```yaml
Type: System.String[]
Parameter Sets: ComputerName
Aliases: Cn

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -ContainerId

Especifica uma matriz de IDs de contêineres. Esse cmdlet Remove sessões para cada um dos contêineres especificados. Use o `docker ps` comando para obter uma lista de IDs de contêiner. Para obter mais informações, consulte a ajuda para o comando [Docker PS](https://docs.docker.com/engine/reference/commandline/ps/) .

```yaml
Type: System.String[]
Parameter Sets: ContainerId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Id

Especifica uma matriz de IDs de sessões.
Esse cmdlet fecha as *PSSessions* com as IDs especificadas.
Digite uma ou mais IDs, separadas por vírgulas, ou use o operador de intervalo (..) para especificar um intervalo de IDs.

Uma ID é um inteiro que identifica exclusivamente a **PSSession** na sessão atual.
É mais fácil lembrar e digitar do que a *InstanceId* , mas só é exclusiva na sessão atual.
Para localizar a ID de uma **PSSession** , execute o cmdlet Get-PSSession sem parâmetros.

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId

Especifica uma matriz de IDs de instância.
Esse cmdlet fecha as **PSSessions** que têm as IDs de instância especificadas.

A ID da instância é um GUID que identifica exclusivamente uma **PSSession** na sessão atual.
A ID da instância é exclusiva, mesmo quando você tem várias sessões em execução em um único computador.

A ID da instância é armazenada na propriedade **InstanceId** do objeto que representa uma **PSSession** .
Para localizar a **InstanceId** das **PSSessions** na sessão atual, digite `Get-PSSession | Format-Table Name, ComputerName, InstanceId` .

```yaml
Type: System.Guid[]
Parameter Sets: InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Especifica uma matriz de nomes amigáveis de sessões.
Esse cmdlet fecha as **PSSessions** que têm os nomes amigáveis especificados.
Caracteres curinga são permitidos.

Como o nome amigável de uma **PSSession** pode não ser exclusivo, ao usar o parâmetro *Name* , considere também usar o parâmetro *WhatIf* ou *Confirm* no comando **Remove-PSSession** .

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Sessão

Especifica os objetos de sessão de **PSSessions** a serem fechados.
Insira uma variável que contenha **PSSessions** ou um comando que cria ou obtém as **PSSessions** , como um comando New-PSSession ou **Get-PSSession** .
Você também pode canalizar um ou mais objetos de sessão para **Remove-PSSession** .

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -VMId

Especifica uma matriz de ID de máquinas virtuais.
Esse cmdlet inicia uma sessão interativa com cada uma das máquinas virtuais especificadas.
Para ver as máquinas virtuais que estão disponíveis para você, use o seguinte comando:

`Get-VM | Select-Object -Property Name, ID`

```yaml
Type: System.Guid[]
Parameter Sets: VMId
Aliases: VMGuid

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMName

Especifica uma matriz de nomes de máquinas virtuais.
Esse cmdlet inicia uma sessão interativa com cada uma das máquinas virtuais especificadas.
Para ver as máquinas virtuais que estão disponíveis para você, use o cmdlet **Get-VM** .

```yaml
Type: System.String[]
Parameter Sets: VMName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Mostra o que aconteceria se o cmdlet fosse executado.
O cmdlet não é executado.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Management. Automation. Runspaces. PSSession

É possível canalizar um objeto de sessão para este cmdlet.

## SAÍDAS

### Nenhum

Este cmdlet não retorna nenhum objeto.

## OBSERVAÇÕES

* O parâmetro *ID* é obrigatório. Para excluir todas as **PSSessions** na sessão atual, digite `Get-PSSession | Remove-PSSession` .
* Uma **PSSession** usa uma conexão persistente com um computador remoto. Crie uma **PSSession** para executar uma série de comandos que compartilham dados. Para obter mais informações, digite `Get-Help about_PSSessions`.
* As **PSSessions** são específicas para a sessão atual. Quando você encerra uma sessão, as **PSSessions** que você criou nessa sessão são fechadas forçosamente.

## LINKS RELACIONADOS

[Connect-PSSession](Connect-PSSession.md)

[Disconnect-PSSession](Disconnect-PSSession.md)

[Enter-PSSession](Enter-PSSession.md)

[Exit-PSSession](Exit-PSSession.md)

[Get-PSSession](Get-PSSession.md)

[Invoke-Command](Invoke-Command.md)

[New-PSSession](New-PSSession.md)

[Receive-PSSession](Receive-PSSession.md)

[about_PSSessions](About/about_PSSessions.md)

[about_Remote](About/about_Remote.md)

