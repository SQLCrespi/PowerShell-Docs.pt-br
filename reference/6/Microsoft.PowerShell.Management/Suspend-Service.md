---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/suspend-service?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Suspend-Service
ms.openlocfilehash: 6e9fd5dd7a5736ef95976cb5195dd1d210d81651
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193376"
---
# Suspend-Service

## SINOPSE
Suspende (pausa) um ou mais serviços em execução.

## SYNTAX

### Inputobject (padrão)

```
Suspend-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Padrão

```
Suspend-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### DisplayName

```
Suspend-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **Suspend-Service** envia uma mensagem de suspensão ao controlador de serviço do Windows para cada um dos serviços especificados.
Ao ser suspenso, o serviço ainda está em execução, mas sua ação é interrompida até ser retomada, por exemplo, por usando Resume-Service cmdlet.
Você pode especificar os serviços por seus nomes de serviço ou nomes de exibição, ou pode usar o parâmetro *InputObject* para passar um objeto de serviço que representa os serviços que você deseja suspender.

## EXEMPLOS

### Exemplo 1: suspender um serviço

```
PS C:\> Suspend-Service -DisplayName "Telnet"
```

Este comando suspende o serviço Telnet (Tlntsvr) no computador local.

### Exemplo 2: exibir o que aconteceria se você suspender os serviços

```
PS C:\> Suspend-Service -Name lanman* -WhatIf
```

Esse comando informa o que aconteceria se você suspendesse os serviços que têm um nome de serviço que começa com o LANMAN.
Para suspender os serviços, execute novamente o comando sem o parâmetro *WhatIf* .

### Exemplo 3: obter e suspender um serviço

```
PS C:\> Get-Service schedule | Suspend-Service
```

Esse comando usa o cmdlet **Get-Service** para obter um objeto que representa o serviço de Agendador de tarefas (agenda) no computador.
O operador de pipeline (|) passa o resultado para **Suspend-Service** , que suspende o serviço.

### Exemplo 4: suspender todos os serviços que podem ser suspensos

```
PS C:\> Get-Service | Where-Object {$_.CanPauseAndContinue -eq "True"} | Suspend-Service -Confirm
```

Este comando suspende todos os serviços no computador que podem ser suspensos.
Ele usa o **Get-Service** para obter objetos que representam os serviços no computador.
O operador de pipeline passa os resultados para o cmdlet Where-Object, que seleciona apenas os serviços que têm um valor de $True para a propriedade **CanPauseAndContinue** .
Outro operador de pipeline passa os resultados para **Suspend-Service** .
O parâmetro *Confirm* solicita sua confirmação antes de suspender cada um dos serviços.

## PARAMETERS

### -DisplayName

Especifica os nomes de exibição dos serviços a serem suspensos.
Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: DisplayName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Excluir

Especifica os serviços a serem omitidos dos serviços especificados.
O valor desse parâmetro qualifica o parâmetro de *nome* .
Insira um elemento Name ou padrão, como "*s".
Caracteres curinga são permitidos.

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

### -Incluir

Especifica os serviços a serem suspensos.
O valor desse parâmetro qualifica o parâmetro de *nome* .
Insira um elemento Name ou padrão, como "*s".
Caracteres curinga são permitidos.

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

### -InputObject

Especifica objetos **ServiceController** que representam os serviços a serem suspensos.
Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.

```yaml
Type: System.ServiceProcess.ServiceController[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Especifica os nomes de serviço dos serviços a serem suspensos.
Caracteres curinga são permitidos.

O nome do parâmetro é opcional.
Você pode usar o *nome* ou seu alias *,* ServiceName ou pode omitir o nome do parâmetro.

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: ServiceName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -PassThru

Retorna um objeto que representa o item com que você está trabalhando.
Por padrão, este cmdlet não gera saída.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### System. ServiceProcess. ServiceController, System. String

É possível canalizar um objeto de serviço ou uma cadeia de caracteres que contém um nome de serviço para esse cmdlet.

## SAÍDAS

### Nenhum, System. ServiceProcess. ServiceController

Esse cmdlet gera um objeto **System. ServiceProcess. ServiceController** que representa o serviço, se você especificar o parâmetro *PassThru* .
Caso contrário, este cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

* O **Suspend-Service** pode controlar os serviços somente quando o usuário atual tem permissão para fazer isso. Se um comando não funcionar corretamente, pode ser que você não tenha as permissões necessárias.
* O **Suspend-Service** pode suspender apenas os serviços que dão suporte à suspensão e retomada. Para determinar se um serviço específico pode ser suspenso, use o cmdlet Get-Service juntamente com a propriedade **CanPauseAndContinue** . Por exemplo, `Get-Service wmi | Format-List Name, CanPauseAndContinue`. Para localizar todos os serviços no computador que podem ser suspensos, digite `Get-Service | Where-Object {$_.CanPauseAndContinue -eq $true}` .
* Para localizar os nomes de serviço e exibir os nomes dos serviços no seu sistema, digite **Get-Service** . Os nomes de serviço aparecem na coluna **nome** e os nomes de exibição aparecem na coluna **DisplayName** .

## LINKS RELACIONADOS

[Get-Service](Get-Service.md)

[New-Service](New-Service.md)

[Restart-Service](Restart-Service.md)

[Resume-Service](Resume-Service.md)

[Set-Service](Set-Service.md)

[Start-Service](Start-Service.md)

[Stop-Service](Stop-Service.md)

[Remove-Service](Remove-Service.md)
