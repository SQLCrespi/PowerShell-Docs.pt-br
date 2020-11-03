---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Service
ms.openlocfilehash: df4fda68508e21700235d2b772c6dd43c8e1fe1e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193920"
---
# Set-Service

## SINOPSE
Inicia, interrompe, suspende um serviço e altera suas propriedades.

## SYNTAX

### Nome (padrão)

```
Set-Service [-ComputerName <String[]>] [-Name] <String> [-DisplayName <String>]
 [-Description <String>] [-StartupType <ServiceStartMode>] [-Status <String>] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### InputObject

```
Set-Service [-ComputerName <String[]>] [-DisplayName <String>] [-Description <String>]
 [-StartupType <ServiceStartMode>] [-Status <String>] [-InputObject <ServiceController>] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Set-Service` cmdlet altera as propriedades de um serviço, como **status** , **Descrição** , **DisplayName** e **StartupType** . `Set-Service` pode iniciar, parar, suspender ou pausar um serviço. Para identificar um serviço, insira seu nome de serviço ou envie um objeto de serviço. Ou envie um nome de serviço ou objeto de serviço pelo pipeline para `Set-Service` .

## EXEMPLOS

### Exemplo 1: alterar um nome de exibição

Neste exemplo, o nome de exibição de um serviço é alterado. Para exibir o nome de exibição original, use `Get-Service` .

```powershell
Set-Service -Name LanmanWorkstation -DisplayName "LanMan Workstation"
```

`Set-Service` usa o parâmetro **Name** para especificar o nome do serviço, **LanmanWorkstation** . O parâmetro **DisplayName** especifica o novo nome de exibição, **estação de trabalho do LanMan** .

### Exemplo 2: alterar o tipo de inicialização dos serviços

Este exemplo mostra como alterar o tipo de inicialização de um serviço.

```powershell
Set-Service -Name BITS -StartupType Automatic
Get-Service BITS | Select-Object -Property Name, StartType, Status
```

```Output
Name  StartType   Status
----  ---------   ------
BITS  Automatic  Running
```

`Set-Service` usa o parâmetro **Name** para especificar o nome do serviço, **bits** . O parâmetro **StartupType** define o serviço como **automático** .

`Get-Service` usa o parâmetro **Name** para especificar o serviço **bits** e envia o objeto para baixo do pipeline. `Select-Object` usa o parâmetro **Property** para exibir o status do serviço **bits** .

### Exemplo 3: alterar a descrição de um serviço

Este exemplo altera a descrição do serviço BITS e exibe o resultado.

O `Get-CimInstance` cmdlet é usado porque retorna um objeto **Win32_Service** que inclui a **Descrição** do serviço.

```powershell
Get-CimInstance Win32_Service -Filter 'Name = "BITS"'  | Format-List  Name, Description
```

```Output
Name        : BITS
Description : Transfers files in the background using idle network bandwidth. If the service is
              disabled, then any applications that depend on BITS, such as Windows Update or MSN
              Explorer, will be unable to automatically download programs and other information.
```

```powershell
Set-Service -Name BITS -Description "Transfers files in the background using idle network bandwidth."
Get-CimInstance Win32_Service -Filter 'Name = "BITS"' | Format-List  Name, Description
```

```Output
Name        : BITS
Description : Transfers files in the background using idle network bandwidth.
```

`Get-CimInstance` envia o objeto para baixo do pipeline para `Format-List` e exibe o nome e a descrição do serviço. Para fins de comparação, o comando é executado antes e depois que a descrição é atualizada.

`Set-Service` usa o parâmetro **Name** para especificar o serviço **bits** . O parâmetro **Description** especifica o texto atualizado para a descrição dos serviços.

### Exemplo 4: iniciar um serviço

Neste exemplo, um serviço é iniciado.

```powershell
Set-Service -Name WinRM -Status Running -PassThru
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  WinRM              Windows Remote Management (WS-Manag...
```

`Set-Service` usa o parâmetro **Name** para especificar o serviço, **WinRM** . O parâmetro **status** usa o valor **em execução** para iniciar o serviço. O parâmetro **PassThru** gera um objeto **ServiceController** que exibe os resultados.

### Exemplo 5: suspender um serviço

Este exemplo usa o pipeline para pausar o serviço.

```powershell
Get-Service -Name Schedule | Set-Service -Status Paused
```

`Get-Service` usa o parâmetro **Name** para especificar o serviço de **agendamento** e envia o objeto para baixo do pipeline. `Set-Service` usa o parâmetro **status** para definir o serviço em **pausa** .

### Exemplo 6: parar um serviço

Este exemplo usa uma variável para parar um serviço.

```powershell
$S = Get-Service -Name Schedule
Set-Service -InputObject $S -Status Stopped
```

`Get-Service` usa o parâmetro **Name** para especificar o serviço, **agenda** . O objeto é armazenado na variável, `$S` . `Set-Service` usa o parâmetro **InputObject** e especifica o objeto armazenado `$S` . O parâmetro **status** define o serviço como **parado** .

## PARAMETERS

### -ComputerName

Especifica um ou mais computadores. Para computadores remotos, digite o nome NetBIOS, um endereço IP ou um nome de domínio totalmente qualificado. Se o parâmetro **ComputerName** não for especificado, o comando será executado no computador local.

Esse parâmetro não depende da comunicação remota do PowerShell. Você pode usar o parâmetro **ComputerName** mesmo que o computador não esteja configurado para executar comandos remotos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: cn

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm

Solicita a confirmação antes de executar `Set-Service` .

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

### -Description

Especifica uma nova descrição para o serviço.

A descrição do serviço aparece em **Gerenciamento do computador, serviços** . A **Descrição** não é uma propriedade do `Get-Service` objeto **ServiceController** . Para ver a descrição do serviço, use `Get-CimInstance` que retorna um objeto **Win32_Service** que representa o serviço.

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

### -DisplayName

Especifica um novo nome para exibição para o serviço.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Especifica um objeto **ServiceController** que representa o serviço a ser alterado. Insira uma variável que contenha o objeto ou digite um comando ou uma expressão que obtenha o objeto, como um `Get-Service` comando. Você pode usar o pipeline para enviar um objeto de serviço para o `Set-Service` .

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

Especifica o nome do serviço a ser alterado. Caracteres curinga não são permitidos. Você pode usar o pipeline para enviar um nome de serviço para `Set-Service` .

```yaml
Type: System.String
Parameter Sets: Name
Aliases: ServiceName, SN

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PassThru

Retorna um objeto **ServiceController** que representa os serviços que foram alterados. Por padrão, o `Set-Service` não gera nenhuma saída.

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

### -StartupType

Define o tipo de inicialização do serviço. Os valores aceitáveis para esse parâmetro são:

- **Automático** -o serviço é iniciado ou iniciado pelo sistema operacional, na inicialização do sistema.
  Se um serviço iniciado automaticamente depende de um serviço iniciado manualmente, o serviço iniciado manualmente também é iniciado automaticamente na inicialização do sistema.
- **Desabilitado** -o serviço está desabilitado e não pode ser iniciado por um usuário ou aplicativo.
- **Manual** -o serviço é iniciado apenas manualmente, por um usuário, usando o Gerenciador de controle de serviço ou por um aplicativo.
- **Inicialização** -indica que o serviço é um driver de dispositivo iniciado pelo carregador do sistema. Esse valor é válido somente para drivers de dispositivo.
- **Sistema** -indica que o serviço é um driver de dispositivo iniciado pela função ' IOInitSystem () '. Esse valor é válido somente para drivers de dispositivo.

 O valor padrão é **automático** .

```yaml
Type: System.ServiceProcess.ServiceStartMode
Parameter Sets: (All)
Aliases: StartMode, SM, ST
Accepted values: Boot, System, Automatic, Manual, Disabled

Required: False
Position: Named
Default value: Automatic
Accept pipeline input: False
Accept wildcard characters: False
```

### -Status

Especifica o status do serviço.

Os valores aceitáveis para esse parâmetro são os seguintes:

- Em **pausa** . Suspende o serviço.
- **Em execução** . Inicia o serviço.
- **Parado** . Interrompe o serviço.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Paused, Running, Stopped

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Mostra o que aconteceria se `Set-Service` for executado. O cmdlet não é executado.

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

Você pode usar o pipeline para enviar um objeto de serviço ou uma cadeia de caracteres que contém um nome de serviço para `Set-Service` .

## SAÍDAS

### System.ServiceProcess.ServiceController

Por padrão, o `Set-Service` não retorna nenhum objeto. Use o parâmetro **PassThru** para gerar um objeto **ServiceController** .

## OBSERVAÇÕES

`Set-Service` requer permissões elevadas. Use a opção **Executar como administrador** .

`Set-Service` Só é possível controlar os serviços quando o usuário atual tem permissões para gerenciar serviços. Se um comando não funcionar corretamente, talvez você não tenha as permissões necessárias.

Para localizar o nome do serviço ou nome de exibição do serviço, use `Get-Service` . Os nomes de serviço estão na coluna **nome** e os nomes de exibição estão na coluna **DisplayName** .

## LINKS RELACIONADOS

[Get-Service](Get-Service.md)

[New-Service](New-Service.md)

[Restart-Service](Restart-Service.md)

[Resume-Service](Resume-Service.md)

[Start-Service](Start-Service.md)

[Stop-Service](Stop-Service.md)

[Suspend-Service](Suspend-Service.md)
