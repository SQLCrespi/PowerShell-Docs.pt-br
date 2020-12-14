---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 11/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Service
ms.openlocfilehash: 758b0a8ef9a5f65f0e7cfa7f3633086cf9f0445d
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94891761"
---
# New-Service

## SINOPSE
Cria um novo serviço do Windows.

## SYNTAX

```
New-Service [-Name] <String> [-BinaryPathName] <String> [-DisplayName <String>] [-Description <String>]
 [-StartupType <ServiceStartMode>] [-Credential <PSCredential>] [-DependsOn <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `New-Service` cmdlet cria uma nova entrada para um serviço do Windows no registro e no banco de dados de serviço. Um novo serviço requer um arquivo executável que é executado durante o serviço.

Os parâmetros desse cmdlet permitem definir o nome de exibição, a descrição, o tipo de inicialização e as dependências do serviço.

## EXEMPLOS

### Exemplo 1: criar um serviço

```powershell
New-Service -Name "TestService" -BinaryPathName '"C:\WINDOWS\System32\svchost.exe -k netsvcs"'
```

Este comando cria um serviço chamado TestService.

### Exemplo 2: criar um serviço que inclui descrição, tipo de inicialização e nome de exibição

```powershell
$params = @{
  Name = "TestService"
  BinaryPathName = '"C:\WINDOWS\System32\svchost.exe -k netsvcs"'
  DependsOn = "NetLogon"
  DisplayName = "Test Service"
  StartupType = "Manual"
  Description = "This is a test service."
}
New-Service @params
```

Este comando cria um serviço chamado TestService. Ele usa os parâmetros de `New-Service` para especificar uma descrição, um tipo de inicialização e um nome de exibição para o novo serviço.

### Exemplo 3: exibir o novo serviço

```powershell
Get-CimInstance -ClassName Win32_Service -Filter "Name='testservice'"
```

```Output
ExitCode  : 0
Name      : testservice
ProcessId : 0
StartMode : Auto
State     : Stopped
Status    : OK
```

Esse comando usa `Get-CimInstance` para obter o objeto de **Win32_Service** para o novo serviço. Este objeto inclui o modo de início e a descrição do serviço.

### Exemplo 4: excluir um serviço

```powershell
sc.exe delete TestService
# - or -
(Get-CimInstance -Class Win32_Service -Filter "name='TestService'").delete()
```

Este exemplo mostra duas maneiras de excluir o serviço TestService. O primeiro comando usa a opção Delete de `Sc.exe` . O segundo comando usa o método **delete** do **Win32_Service** objetos que `Get-CimInstance` retorna.

## PARAMETERS

### -BinaryPathName

Especifica o caminho do arquivo executável para o serviço. Este parâmetro é necessário.

O caminho totalmente qualificado para o arquivo binário do serviço. Se o caminho contiver um espaço, ele deverá estar entre aspas para que seja interpretado corretamente. Por exemplo, `d:\my share\myservice.exe` deve ser especificado como `'"d:\my share\myservice.exe"'` .

O caminho também pode incluir argumentos para um serviço de início automático. Por exemplo, `'"d:\myshare\myservice.exe arg1 arg2"'`. Esses argumentos são passados para o ponto de entrada de serviço.

Para obter mais informações, consulte o parâmetro **lpBinaryPathName** da API [CreateServiceW](/windows/win32/api/winsvc/nf-winsvc-createservicew) .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Especifica a conta usada pelo serviço como a [conta de logon de serviço](/windows/desktop/ad/about-service-logon-accounts).

Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01**, ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet. Se você digitar um nome de usuário, esse cmdlet solicitará uma senha.

As credenciais são armazenadas em um objeto [PSCredential](/dotnet/api/system.management.automation.pscredential) e a senha é armazenada como uma [SecureString](/dotnet/api/system.security.securestring).

> [!NOTE]
> Para obter mais informações sobre a proteção de dados **SecureString** , consulte [quão seguro é a SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

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

### -Depende

Especifica os nomes de outros serviços dos quais o novo serviço depende. Para digitar vários nomes de serviço, use uma vírgula para separar os nomes.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description

Especifica uma descrição do serviço.

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

Especifica um nome de exibição para o serviço.

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

### -Name

Especifica o nome do serviço. Este parâmetro é necessário.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ServiceName

Required: True
Position: 0
Default value: None
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

 O valor padrão é **automático**.

```yaml
Type: System.ServiceProcess.ServiceStartMode
Parameter Sets: (All)
Aliases:
Accepted values: Boot, System, Automatic, Manual, Disabled

Required: False
Position: Named
Default value: Automatic
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

### Nenhum

Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### System.ServiceProcess.ServiceController

Esse cmdlet retorna um objeto que representa o novo serviço.

## OBSERVAÇÕES

Para executar esse cmdlet, inicie o PowerShell usando a opção **Executar como administrador** .

Para excluir um serviço, use Sc.exe ou use o `Get-CimInstance` cmdlet para obter o **Win32_Service** objeto que representa o serviço e, em seguida, use o método **delete** para excluir o serviço. O objeto que `Get-Service` retorna não tem um método Delete.

## LINKS RELACIONADOS

[Get-Service](Get-Service.md)

[Restart-Service](Restart-Service.md)

[Resume-Service](Resume-Service.md)

[Set-Service](Set-Service.md)

[Start-Service](Start-Service.md)

[Stop-Service](Stop-Service.md)

[Suspend-Service](Suspend-Service.md)
