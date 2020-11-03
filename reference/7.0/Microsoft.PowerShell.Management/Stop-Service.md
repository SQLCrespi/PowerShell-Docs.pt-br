---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-service?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Service
ms.openlocfilehash: 2ae91494b87b9c4cce13d1a41bcbce72405cd0dd
ms.sourcegitcommit: 69b08b28ee2ef3168065672a23b9b6f0c578c95b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2020
ms.locfileid: "93195300"
---
# Stop-Service

## SINOPSE
Interrompe um ou mais serviços em execução.

## SYNTAX

### Inputobject (padrão)

```
Stop-Service [-Force] [-NoWait] [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Padrão

```
Stop-Service [-Force] [-NoWait] [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DisplayName

```
Stop-Service [-Force] [-NoWait] [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **Stop-Service** envia uma mensagem de parada ao controlador de serviço do Windows para cada um dos serviços especificados.
Você pode especificar os serviços por seus nomes de serviço ou nomes de exibição, ou pode usar o parâmetro **InputObject** para passar um objeto de serviço que representa o serviço que você deseja parar.

## EXEMPLOS

### Exemplo 1: parar um serviço no computador local

```
PS C:\> Stop-Service -Name "sysmonlog"
```

Esse comando para os Alertas e Logs de Desempenho (SysmonLog) do serviço no computador local.

### Exemplo 2: parar um serviço usando o nome de exibição

```
PS C:\> Get-Service -DisplayName "telnet" | Stop-Service
```

Esse comando para o serviço Telnet no computador local.
O comando usa **Get-Service** para obter um objeto que representa o serviço Telnet.
O operador de pipeline (|) canaliza o objeto para **Stop-Service** , o que interrompe o serviço.

### Exemplo 3: parar um serviço que tem serviços dependentes

```
PS C:\> Get-Service -Name "iisadmin" | Format-List -Property Name, DependentServices
PS C:\> Stop-Service -Name "iisadmin" -Force -Confirm
```

Este exemplo interrompe o serviço IISAdmin no computador local.
Como a interrupção desse serviço também interrompe os serviços que dependem do serviço IISAdmin, é melhor preceder o **serviço Stop** com um comando que lista os serviços que dependem do serviço IISAdmin.

O primeiro comando lista os serviços que dependem do IISAdmin.
Ele usa **Get-Service** para obter um objeto que representa o serviço IISAdmin.
O operador de pipeline (|) passa o resultado para o cmdlet Format-List.
O comando usa o parâmetro *Property* de **Format-List** para listar apenas as propriedades **Name** e **DependentServices** do serviço.

O segundo comando interrompe o serviço IISAdmin.
O parâmetro *Force* é necessário para interromper um serviço que tem serviços dependentes.
O comando usa o parâmetro *Confirm* para solicitar a confirmação do usuário antes de parar cada serviço.

## PARAMETERS

### -DisplayName

Especifica os nomes de exibição dos serviços a serem interrompidos.
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

Especifica os serviços que esse cmdlet omite.
O valor desse parâmetro qualifica o parâmetro de *nome* .
Insira um elemento de nome ou padrão, como s *.
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

### -Force

Força o cmdlet a parar um serviço mesmo que esse serviço tenha serviços dependentes.

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

### -Incluir

Especifica os serviços que este cmdlet interrompe.
O valor desse parâmetro qualifica o parâmetro de *nome* .
Insira um elemento de nome ou padrão, como s *.
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

Especifica objetos **ServiceController** que representam os serviços a serem interrompidos.
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

Especifica os nomes de serviço dos serviços a serem interrompidos.
Caracteres curinga são permitidos.

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

### -Nowait

Indica que esse cmdlet usa a opção sem espera.

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

### -PassThru

Retorna um objeto que representa o serviço.
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

É possível canalizar um objeto de serviço ou uma cadeia de caracteres que contém o nome de um serviço para esse cmdlet.

## SAÍDAS

### Nenhum, System. ServiceProcess. ServiceController

Esse cmdlet gera um objeto **System. ServiceProcess. ServiceController** que representa o serviço, se você usar o parâmetro *PassThru* .
Caso contrário, este cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

* Você também pode se referir ao **Stop-Service** por seu alias interno, **spsv** . Para obter mais informações, consulte about_Aliases.

  O **Stop-Service** pode controlar serviços somente quando o usuário atual tem permissão para fazer isso.
Se um comando não funcionar corretamente, pode ser que você não tenha as permissões necessárias.

  Para localizar os nomes de serviço e exibir os nomes dos serviços no seu sistema, digite `Get-Service` .
Os nomes de serviço aparecem na coluna **nome** e os nomes de exibição aparecem na coluna **DisplayName** .


## LINKS RELACIONADOS

[Get-Service](Get-Service.md)

[New-Service](New-Service.md)

[Restart-Service](Restart-Service.md)

[Resume-Service](Resume-Service.md)

[Set-Service](Set-Service.md)

[Start-Service](Start-Service.md)

[Suspend-Service](Suspend-Service.md)

[Remove-Service](Remove-Service.md)
