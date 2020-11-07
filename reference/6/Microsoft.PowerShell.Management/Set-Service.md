---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-service?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Service
ms.openlocfilehash: a5c156dcf83b3c60123b0bdde002c8657081602e
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94343752"
---
# Set-Service

## SINOPSE
Inicia, interrompe, suspende um serviço e altera suas propriedades.

## SYNTAX

### Nome (padrão)

```
Set-Service [-Name] <String> [-DisplayName <String>] [-Credential <PSCredential>]
 [-Description <String>] [-StartupType <ServiceStartupType>] [-Status <String>] [-Force] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject

```
Set-Service [-InputObject] <ServiceController> [-DisplayName <String>] [-Credential <PSCredential>]
 [-Description <String>] [-StartupType <ServiceStartupType>] [-Status <String>] [-Force] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Set-Service` cmdlet altera as propriedades de um serviço, como **status** , **Descrição** , **DisplayName** e **StartupType**. `Set-Service` pode iniciar, parar, suspender ou pausar um serviço. Para identificar um serviço, insira seu nome de serviço ou envie um objeto de serviço. Ou envie um nome de serviço ou objeto de serviço pelo pipeline para `Set-Service` .

## EXEMPLOS

### Exemplo 1: alterar um nome de exibição

Neste exemplo, o nome de exibição de um serviço é alterado. Para exibir o nome de exibição original, use `Get-Service` .

```powershell
Set-Service -Name LanmanWorkstation -DisplayName "LanMan Workstation"
```

`Set-Service` usa o parâmetro **Name** para especificar o nome do serviço, **LanmanWorkstation**. O parâmetro **DisplayName** especifica o novo nome de exibição, **estação de trabalho do LanMan**.

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

`Set-Service` usa o parâmetro **Name** para especificar o nome do serviço, **bits**. O parâmetro **StartupType** define o serviço como **automático**.

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

`Set-Service` usa o parâmetro **Name** para especificar o serviço, **WinRM**. O parâmetro **status** usa o valor **em execução** para iniciar o serviço. O parâmetro **PassThru** gera um objeto **ServiceController** que exibe os resultados.

### Exemplo 5: suspender um serviço

Este exemplo usa o pipeline para pausar o serviço.

```powershell
Get-Service -Name Schedule | Set-Service -Status Paused
```

`Get-Service` usa o parâmetro **Name** para especificar o serviço de **agendamento** e envia o objeto para baixo do pipeline. `Set-Service` usa o parâmetro **status** para definir o serviço em **pausa**.

### Exemplo 6: parar um serviço

Este exemplo usa uma variável para parar um serviço.

```powershell
$S = Get-Service -Name Schedule
Set-Service -InputObject $S -Status Stopped
```

`Get-Service` usa o parâmetro **Name** para especificar o serviço, **agenda**. O objeto é armazenado na variável, `$S` . `Set-Service` usa o parâmetro **InputObject** e especifica o objeto armazenado `$S` . O parâmetro **status** define o serviço como **parado**.

### Exemplo 7: parar um serviço em um sistema remoto

Este exemplo interrompe um serviço em um computador remoto.
Para obter mais informações, consulte [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).

```powershell
$Cred = Get-Credential
$S = Get-Service -Name Schedule
Invoke-Command -ComputerName server01.contoso.com -Credential $Cred -ScriptBlock {
  Set-Service -InputObject $S -Status Stopped
}
```

`Get-Credential` solicita um nome de usuário e uma senha e armazena as credenciais na `$Cred` variável. `Get-Service` usa o parâmetro **Name** para especificar o serviço de **agendamento** . O objeto é armazenado na variável, `$S` .

`Invoke-Command` usa o parâmetro **ComputerName** para especificar um computador remoto. O parâmetro **Credential** usa a `$Cred` variável para fazer logon no computador. O **scriptblock** chama `Set-Service` . O parâmetro **InputObject** especifica o objeto de serviço armazenado `$S` . O parâmetro **status** define o serviço como **parado**.

### Exemplo 8: alterar a credencial de um serviço

Este exemplo altera as credenciais que são usadas para gerenciar um serviço.

```powershell
$credential = Get-Credential
Set-Service -Name Schedule -Credential $credential
```

`Get-Credential` solicita um nome de usuário e uma senha e armazena as credenciais na `$credential` variável. `Set-Service` usa o parâmetro **Name** para especificar o serviço de **agendamento** . O parâmetro **Credential** usa a `$credential` variável e atualiza o serviço de **agendamento** .

## PARAMETERS

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

### -Credential

Especifica a conta usada pelo serviço como a [conta de logon de serviço](/windows/desktop/ad/about-service-logon-accounts).

Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** , ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet. Se você digitar um nome de usuário, esse cmdlet solicitará uma senha.

As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).

> [!NOTE]
> Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

Esse parâmetro foi introduzido no PowerShell 6,0.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description

Especifica uma nova descrição para o serviço.

A descrição do serviço aparece em **Gerenciamento do computador, serviços**. A **Descrição** não é uma propriedade do `Get-Service` objeto **ServiceController** . Para ver a descrição do serviço, use `Get-CimInstance` que retorna um objeto **Win32_Service** que representa o serviço.

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

### -Force

Especifica o modo de interrupção do serviço. Esse parâmetro só funciona quando `-Status Stopped` é usado. Se habilitada, `Set-Service` o interrompe os serviços dependentes antes que o serviço de destino seja interrompido. Por padrão, as exceções são geradas quando outros serviços em execução dependem do serviço de destino.

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

### -InputObject

Especifica um objeto **ServiceController** que representa o serviço a ser alterado. Insira uma variável que contenha o objeto ou digite um comando ou uma expressão que obtenha o objeto, como um `Get-Service` comando. Você pode usar o pipeline para enviar um objeto de serviço para o `Set-Service` .

```yaml
Type: System.ServiceProcess.ServiceController
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
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

Especifica o modo de início do serviço.

Os valores aceitáveis para esse parâmetro são os seguintes:

- **Automático** -o serviço é iniciado ou iniciado pelo sistema operacional, na inicialização do sistema.
  Se um serviço iniciado automaticamente depende de um serviço iniciado manualmente, o serviço iniciado manualmente também é iniciado automaticamente na inicialização do sistema.
- **AutomaticDelayedStart** -inicia logo após a inicialização do sistema.
- **Desabilitado** -o serviço está desabilitado e não pode ser iniciado por um usuário ou aplicativo.
- **Inválidos** -não tem efeito. O cmdlet não retorna um erro, mas o StartupType do serviço não é alterado.
- **Manual** -o serviço é iniciado apenas manualmente, por um usuário, usando o Gerenciador de controle de serviço ou por um aplicativo.

```yaml
Type: Microsoft.PowerShell.Commands.ServiceStartupType
Parameter Sets: (All)
Aliases: StartMode, SM, ST
Accepted values: Automatic, AutomaticDelayedStart, Disabled, InvalidValue, Manual

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Status

Especifica o status do serviço.

Os valores aceitáveis para esse parâmetro são os seguintes:

- Em **pausa**. Suspende o serviço.
- **Em execução**. Inicia o serviço.
- **Parado**. Interrompe o serviço.

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

Esse cmdlet só está disponível em plataformas Windows.

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

[Remove-Service](Remove-Service.md)
