---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-service?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Service
ms.openlocfilehash: a79bcdaa60c420c4436276749c1b4d298158f8a6
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "94343004"
---
# Start-Service

## SINOPSE
Inicia um ou mais serviços interrompidos.

## SYNTAX

### Inputobject (padrão)

```
Start-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Padrão

```
Start-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### DisplayName

```
Start-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Start-Service` cmdlet envia uma mensagem de início para o controlador de serviço do Windows para cada um dos serviços especificados. Se um serviço estiver sendo executado, a mensagem será ignorada sem erro. Você pode especificar os serviços por seus nomes de serviço ou nomes de exibição, ou pode usar o parâmetro **InputObject** para fornecer um objeto de serviço que represente os serviços que você deseja iniciar.

## EXEMPLOS

### Exemplo 1: iniciar um serviço usando seu nome

Este exemplo inicia o serviço EventLog no computador local. O parâmetro **Name** identifica o serviço pelo nome do serviço.

```powershell
Start-Service -Name "eventlog"
```

### Exemplo 2: exibir informações sem iniciar um serviço

Este exemplo mostra o que aconteceria se você iniciasse os serviços que têm um nome de exibição que inclui "remoto".

```powershell
Start-Service -DisplayName *remote* -WhatIf
```

O parâmetro **DisplayName** identifica os serviços por seu nome de exibição, em vez de seu nome de serviço. O parâmetro **WhatIf** faz com que o cmdlet exiba o que aconteceria quando você executa o comando, mas não faz alterações.

### Exemplo 3: iniciar um serviço e registrar a ação em um arquivo de texto

Este exemplo inicia o serviço de Instrumentação de Gerenciamento do Windows (WMI) no computador e adiciona um registro da ação ao arquivo de services.txt.

```powershell
$s = Get-Service wmi
Start-Service -InputObject $s -PassThru | Format-List >> services.txt
```

Primeiro, usamos `Get-Service` para obter um objeto que representa o serviço WMI e armazená-lo `$s` na variável. Em seguida, iniciamos o serviço. Sem o parâmetro **PassThru** , o não `Start-Service` cria nenhuma saída. O operador de pipeline (|) passa a saída do objeto pelo `Start-Service` para o `Format-List` cmdlet para formatar o objeto como uma lista de suas propriedades. O operador de redirecionamento de acréscimo ( \> \> ) redireciona a saída para o arquivo de services.txt. A saída é adicionada ao final do arquivo existente.

### Exemplo 4: iniciar um serviço desabilitado

Este exemplo mostra como iniciar um serviço quando o tipo de início do serviço é **desabilitado**.

```
PS> Start-Service tlntsvr
Start-Service : Service 'Telnet (TlntSvr)' cannot be started due to the following error: Cannot start service TlntSvr on computer '.'.
At line:1 char:14
+ Start-Service  <<<< tlntsvr

PS> Get-CimInstance win32_service | Where-Object Name -eq "tlntsvr"
ExitCode  : 0
Name      : TlntSvr
ProcessId : 0
StartMode : Disabled
State     : Stopped
Status    : OK

PS> Set-Service tlntsvr -StartupType manual
PS> Start-Service tlntsvr
```

A primeira tentativa de iniciar o serviço Telnet (TlntSvr) falha. O `Get-CimInstance` comando mostra que a propriedade **startMode** do serviço TlntSvr está **desabilitada**. O `Set-Service` cmdlet altera o tipo de início para **manual**. Agora, podemos enviar o comando novamente `Start-Service` . Desta vez, o comando terá êxito. Para verificar se o comando foi bem-sucedido, execute `Get-Service` .

## PARAMETERS

### -DisplayName

Especifica os nomes de exibição dos serviços a serem iniciados. Caracteres curinga são permitidos.

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

Especifica os serviços que esse cmdlet omite. O valor desse parâmetro qualifica o parâmetro de **nome** . Insira um elemento de nome ou padrão, como `s*` . Caracteres curinga são permitidos.

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

Especifica os serviços que este cmdlet inicia. O valor desse parâmetro qualifica o parâmetro de **nome** . Insira um elemento de nome ou padrão, como `s*` . Caracteres curinga são permitidos.

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

Especifica objetos **ServiceController** que representam os serviços a serem iniciados. Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.

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

Especifica os nomes de serviço para o serviço a ser iniciado.

O nome do parâmetro é opcional. Você pode usar o **nome** ou seu alias **,** ServiceName ou pode omitir o nome do parâmetro.

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: ServiceName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PassThru

Retorna um objeto que representa o serviço. Por padrão, este cmdlet não gera saída.

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

É possível canalizar objetos que representam os serviços ou cadeias de caracteres que contêm os nomes de serviço para esse cmdlet.

## SAÍDAS

### Nenhum, System. ServiceProcess. ServiceController

Esse cmdlet gera um objeto **System. ServiceProcess. ServiceController** que representa o serviço, se você especificar **PassThru**. Caso contrário, este cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

Esse cmdlet só está disponível em plataformas Windows.

- Você também pode consultar `Start-Service` por seu alias interno, `sasv` . Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).
- `Start-Service` pode controlar os serviços somente se o usuário atual tiver permissão para fazer isso. Se um comando não funcionar corretamente, pode ser que você não tenha as permissões necessárias.
- Para localizar os nomes de serviço e exibir os nomes dos serviços no seu sistema, digite `Get-Service` .
  Os nomes de serviço aparecem na coluna **nome** e os nomes de exibição aparecem na coluna **DisplayName** .
- Você pode iniciar somente os serviços que têm um tipo de início manual, automático ou automático (início atrasado). Você não pode iniciar os serviços que têm um tipo de início desabilitado. Se um `Start-Service` comando falhar com a mensagem `Cannot start service \<service-name\> on computer` , use `Get-CimInstance` para localizar o tipo de início do serviço e, se necessário, use o `Set-Service` cmdlet para alterar o tipo de início do serviço.
- Alguns serviços, como Logs e Alertas de Desempenho (SysmonLog), serão interrompidos automaticamente se não tiverem nenhum trabalho a fazer. Quando o PowerShell inicia um serviço que se interrompe quase imediatamente, ele exibe a seguinte mensagem: `Service \<display-name\> start failed.`

## LINKS RELACIONADOS

[Get-Service](Get-Service.md)

[New-Service](New-Service.md)

[Restart-Service](Restart-Service.md)

[Resume-Service](Resume-Service.md)

[Set-Service](Set-Service.md)

[Stop-Service](Stop-Service.md)

[Suspend-Service](Suspend-Service.md)

[Remove-Service](Remove-Service.md)
