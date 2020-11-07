---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-service?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Service
ms.openlocfilehash: d5189dfb39e9505efd39bfd55791d512e40a7c3e
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94343786"
---
# Remove-Service

## SINOPSE
Remove um serviço do Windows.

## SYNTAX

### Nome (padrão)

```
Remove-Service [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject

```
Remove-Service [-InputObject <ServiceController>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Remove-Service` cmdlet Remove um serviço do Windows no registro e no banco de dados do serviço.

O `Remove-Service` cmdlet foi introduzido no PowerShell 6,0.

## EXEMPLOS

### Exemplo 1: remover um serviço

Isso remove um serviço chamado TestService.

```powershell
Remove-Service -Name "TestService"
```

### Exemplo 2: remover um serviço usando o nome de exibição

Este exemplo remove um serviço chamado TestService. O comando usa `Get-Service` para obter um objeto que representa o serviço TestService usando o nome de exibição. O operador de pipeline ( `|` ) canaliza o objeto para `Remove-Service` , que remove o serviço.

```powershell
Get-Service -DisplayName "Test Service" | Remove-Service
```

## PARAMETERS

### -InputObject

Especifica objetos **ServiceController** que representam os serviços a serem removidos. Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.

```yaml
Type: System.ServiceProcess.ServiceController
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Especifica os nomes de serviço dos serviços a serem removidos. Caracteres curinga são permitidos.

```yaml
Type: System.String
Parameter Sets: Name
Aliases: ServiceName, SN

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
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

Mostra o que aconteceria se o cmdlet fosse executado. O cmdlet não é executado.

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

### Nenhum

Este cmdlet não retorna nenhuma saída.

## OBSERVAÇÕES

Esse cmdlet só está disponível em plataformas Windows.

Para executar esse cmdlet, inicie o PowerShell usando a opção **Executar como administrador** .

## LINKS RELACIONADOS

[Get-Service](Get-Service.md)

[Restart-Service](Restart-Service.md)

[Resume-Service](Resume-Service.md)

[Set-Service](Set-Service.md)

[Start-Service](Start-Service.md)

[Stop-Service](Stop-Service.md)

[Suspend-Service](Suspend-Service.md)
