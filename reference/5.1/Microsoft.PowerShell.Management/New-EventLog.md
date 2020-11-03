---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 01/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-EventLog
ms.openlocfilehash: 61fafc0670a24fd6ca057e4cf0c7179d90446b07
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193971"
---
# New-EventLog

## SINOPSE
Cria um novo log de eventos e uma nova origem do evento em um computador local ou remoto.

## SYNTAX

```
New-EventLog [-LogName] <string> [-Source] <string[]> [[-ComputerName] <string[]>]
  [-CategoryResourceFile <string>] [-MessageResourceFile <string>] [-ParameterResourceFile <string>]
  [<CommonParameters>]
```

## DESCRIPTION

Este cmdlet cria um novo log clássico de eventos em um computador local ou remoto. Ele também pode registrar uma origem de evento que grava no novo log ou em um log existente.

Os cmdlets que contêm o substantivo EventLog (os cmdlets do log de eventos) só funcionam em logs clássicos de eventos.
Para obter eventos de logs que usam a tecnologia de log de eventos do Windows no Windows Vista e versões posteriores do Windows, use o `Get-WinEvent` .

## EXEMPLOS

### Exemplo 1-criar um novo log de eventos

Este comando cria o log de eventos TestLog no computador local e registra uma nova origem para ele.

```powershell
New-EventLog -source TestApp -LogName TestLog -MessageResourceFile C:\Test\TestApp.dll
```

### Exemplo 2-adicionar uma nova origem do evento a um log existente

Este comando adiciona uma nova origem de eventos, NewTestApp, no log de aplicativo do computador remoto Servidor01.

```powershell
$file = "C:\Program Files\TestApps\NewTestApp.dll"
New-EventLog -ComputerName Server01 -Source NewTestApp -LogName Application -MessageResourceFile $file -CategoryResourceFile $file
```

O comando requer que o arquivo NewTestApp.dll esteja localizado no computador Servidor01.

## PARAMETERS

### -CategoryResourceFile

Especifica o caminho para o arquivo que contém as cadeias de categorias para os eventos da origem. Esse arquivo também é conhecido como o arquivo de mensagem de categoria.

O arquivo deve estar presente no computador no qual o log de eventos está sendo criado. Este parâmetro não cria nem move arquivos.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CRF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Cria os novos logs de eventos nos computadores especificados. O padrão é o computador local.

O nome NetBIOS, o endereço IP ou o nome de domínio totalmente qualificado de um computador remoto.
Para especificar o computador local, digite o nome do computador, um ponto (.) ou "localhost".

Esse parâmetro não depende da comunicação remota do PowerShell. Você pode usar o parâmetro **ComputerName** de `Get-EventLog` mesmo que o computador não esteja configurado para executar comandos remotos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 3
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogName

Especifica o nome do log de eventos.

Se o log não existir, o `New-EventLog` criará o log e usará esse valor para as propriedades **log** e **LogDisplayName** do novo log de eventos. Se o log existir, o registrará `New-EventLog` uma nova origem para o log de eventos.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MessageResourceFile

Especifica o caminho para o arquivo que contém as cadeias de formatação de mensagens para os eventos da origem.
Esse arquivo também é conhecido como o arquivo de mensagem de evento.

O arquivo deve estar presente no computador no qual o log de eventos está sendo criado.
Este parâmetro não cria nem move arquivos.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: MRF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParameterResourceFile

Especifica o caminho para o arquivo que contém cadeias de caracteres usadas para substituições de parâmetro nas descrições de eventos. Este arquivo também é conhecido como o arquivo de mensagem de parâmetro.

O arquivo deve estar presente no computador no qual o log de eventos está sendo criado.
Este parâmetro não cria nem move arquivos.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PRF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source

Especifica os nomes das origens do log de eventos, como os programas aplicativos que gravam no log de eventos. Este parâmetro é necessário.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: SRC

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Não é possível redirecionar a entrada para este cmdlet.

## SAÍDAS

### System. Diagnostics. EventLogEntry

## OBSERVAÇÕES

Para usar `New-EventLog` o no Windows Vista e versões posteriores do Windows, abra o PowerShell com a opção "executar como administrador".

Para criar uma origem de evento no Windows Vista, Windows XP Professional ou Windows Server 2003, você deve ser um membro do grupo Administradores do computador.

Quando você cria um novo log de eventos e uma nova origem de evento, o sistema registra a nova origem para o novo log, mas o log não é criado até que a primeira entrada seja gravada nele.

O sistema operacional armazena os logs de eventos como arquivos.

Quando você cria um novo log de eventos, o arquivo associado é armazenado no `$env:SystemRoot\System32\Config` diretório no computador especificado.

O nome do arquivo é os oito primeiros caracteres da propriedade **log** com uma extensão de nome de arquivo. evt.

## LINKS RELACIONADOS

[Clear-EventLog](Clear-EventLog.md)

[Get-EventLog](Get-EventLog.md)

[Get-WinEvent](../Microsoft.PowerShell.Diagnostics/Get-WinEvent.md)

[Limit-EventLog](Limit-EventLog.md)

[New-EventLog](New-EventLog.md)

[Remove-EventLog](Remove-EventLog.md)

[Show-EventLog](Show-EventLog.md)

[Write-EventLog](Write-EventLog.md)
