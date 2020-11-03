---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 3/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-EventLog
ms.openlocfilehash: ab1a97dc3c78bbfdcc239fd573ef3b1f839e2b21
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194183"
---
# Get-EventLog

## SINOPSE
Obtém os eventos em um log de eventos ou uma lista dos logs de eventos no computador local ou nos computadores remotos.

## SYNTAX

### LogName (padrão)

```
Get-EventLog [-LogName] <String> [-ComputerName <String[]>] [-Newest <Int32>] [-After <DateTime>]
 [-Before <DateTime>] [-UserName <String[]>] [[-InstanceId] <Int64[]>] [-Index <Int32[]>]
 [-EntryType <String[]>] [-Source <String[]>] [-Message <String>] [-AsBaseObject]
 [<CommonParameters>]
```

### Lista

```
Get-EventLog [-ComputerName <String[]>] [-List] [-AsString] [<CommonParameters>]
```

## DESCRIPTION

O `Get-EventLog` cmdlet obtém eventos e logs de eventos de computadores locais e remotos. Por padrão, o `Get-EventLog` Obtém logs do computador local. Para obter logs de computadores remotos, use o parâmetro **ComputerName** .

Você pode usar os `Get-EventLog` parâmetros e os valores de propriedade para pesquisar eventos. O cmdlet obtém os eventos que correspondem aos valores de propriedade especificados.

Os cmdlets do PowerShell que contêm o `EventLog` substantivo só funcionam em logs de eventos clássicos do Windows, como aplicativo, sistema ou segurança. Para obter logs que usam a tecnologia de log de eventos do Windows no Windows Vista e versões posteriores do Windows, use `Get-WinEvent` .

> [!NOTE]
> `Get-EventLog` usa uma API do Win32 que é preterida. Os resultados podem não ser precisos. `Get-WinEvent`Em vez disso, use o cmdlet.

## EXEMPLOS

### Exemplo 1: obter logs de eventos no computador local

Este exemplo exibe a lista de logs de eventos que estão disponíveis no computador local. Os nomes na coluna log são usados com o parâmetro **LogName** para especificar qual log é pesquisado em busca de eventos.

```powershell
Get-EventLog -List
```

```Output
Max(K)   Retain   OverflowAction      Entries  Log
------   ------   --------------      -------  ---
15,168        0   OverwriteAsNeeded   20,792   Application
15,168        0   OverwriteAsNeeded   12,559   System
15,360        0   OverwriteAsNeeded   11,173   Windows PowerShell
```

O `Get-EventLog` cmdlet usa o parâmetro **list** para exibir os logs disponíveis.

### Exemplo 2: obter entradas recentes de um log de eventos no computador local

Este exemplo obtém entradas recentes do log de eventos do sistema.

```powershell
Get-EventLog -LogName System -Newest 5
```

```Output
Index   Time          EntryType    Source              InstanceID   Message
-----   ----          ---------    ------              ----------   -------
13820   Jan 17 19:16  Error        DCOM                     10016   The description for Event...
13819   Jan 17 19:08  Error        DCOM                     10016   The description for Event...
13818   Jan 17 19:06  Information  Service Control...  1073748864   The start type of the Back...
13817   Jan 17 19:05  Error        DCOM                     10016   The description for Event...
13815   Jan 17 19:03  Information  Microsoft-Windows...        35   The time service is now sync...
```

O `Get-EventLog` cmdlet usa o parâmetro **LogName** para especificar o log de eventos do sistema. O parâmetro **mais recente** retorna os cinco eventos mais recentes.

### Exemplo 3: localizar todas as fontes para um número específico de entradas em um log de eventos

Este exemplo mostra como localizar todas as fontes incluídas nas 1000 entradas mais recentes no log de eventos do sistema.

```powershell
$Events = Get-EventLog -LogName System -Newest 1000
$Events | Group-Object -Property Source -NoElement | Sort-Object -Property Count -Descending
```

```Output
Count   Name
-----   ----
  110   DCOM
   65   Service Control Manager
   51   Microsoft-Windows-Kern...
   14   EventLog
   14   BTHUSB
   13   Win32k
```

O `Get-EventLog` cmdlet usa o parâmetro **LogName** para especificar o log do sistema. O parâmetro **mais recente** seleciona os 1000 eventos mais recentes. Os objetos de evento são armazenados na `$Events` variável. Os `$Events` objetos são enviados para o pipeline para o `Group-Object` cmdlet.
`Group-Object` usa o parâmetro **Property** para agrupar os objetos por origem e conta o número de objetos para cada fonte. O parâmetro **NoElement** remove os membros do grupo da saída.
O `Sort-Object` cmdlet usa o parâmetro **Property** para classificar pela contagem de cada nome de origem.
O parâmetro **decrescente** classifica a lista em ordem por contagem, da mais alta para a mais baixa.

### Exemplo 4: obter eventos de erro de um log de eventos específico

Este exemplo obtém eventos de erro do log de eventos do sistema.

```powershell
Get-EventLog -LogName System -EntryType Error
```

```Output
Index Time          EntryType   Source  InstanceID Message
----- ----          ---------   ------  ---------- -------
13296 Jan 16 13:53  Error       DCOM    10016 The description for Event ID '10016' in Source...
13291 Jan 16 13:51  Error       DCOM    10016 The description for Event ID '10016' in Source...
13245 Jan 16 11:45  Error       DCOM    10016 The description for Event ID '10016' in Source...
13230 Jan 16 11:07  Error       DCOM    10016 The description for Event ID '10016' in Source...
```

O `Get-EventLog` cmdlet usa o parâmetro **LogName** para especificar o log do sistema. O parâmetro **EntryType** filtra os eventos para mostrar apenas os eventos de erro.

### Exemplo 5: obter eventos de um log de eventos com uma InstanceId e um valor de origem

Este exemplo obtém eventos do log do sistema para um InstanceId e uma origem específicos.

```powershell
Get-EventLog -LogName System -InstanceId 10016 -Source DCOM
```

```Output
Index Time          EntryType  Source  InstanceID  Message
----- ----          ---------  ------  ----------  -------
13245 Jan 16 11:45  Error      DCOM         10016  The description for Event ID '10016' in Source...
13230 Jan 16 11:07  Error      DCOM         10016  The description for Event ID '10016' in Source...
13219 Jan 16 10:00  Error      DCOM         10016  The description for Event ID '10016' in Source...
```

O `Get-EventLog` cmdlet usa o parâmetro **LogName** para especificar o log do sistema. O parâmetro **InstanceId** seleciona os eventos com a ID de instância especificada. O parâmetro **Source** especifica a propriedade de evento.

### Exemplo 6: obter eventos de vários computadores

Esse comando obtém os eventos do log de eventos do sistema em três computadores: Server01, Server02 e Server03.

```powershell
Get-EventLog -LogName System -ComputerName Server01, Server02, Server03
```

O `Get-EventLog` cmdlet usa o parâmetro **LogName** para especificar o log do sistema. O parâmetro **ComputerName** usa uma cadeia de caracteres separada por vírgulas para listar os computadores dos quais você deseja obter os logs de eventos.

### Exemplo 7: obter todos os eventos que incluem uma palavra específica na mensagem

Esse comando obtém todos os eventos no log de eventos do sistema que contêm uma palavra específica na mensagem do evento. É possível que o valor do parâmetro de **mensagem** especificado seja incluído no conteúdo da mensagem, mas não seja exibido no console do PowerShell.

```powershell
Get-EventLog -LogName System -Message *description*
```

```Output
Index Time          EntryType   Source       InstanceID   Message
----- ----          ---------   ------       ----------   -------
13821 Jan 17 19:17  Error       DCOM              10016   The description for Event ID '10016'...
13820 Jan 17 19:16  Error       DCOM              10016   The description for Event ID '10016'...
13819 Jan 17 19:08  Error       DCOM              10016   The description for Event ID '10016'...
```

O `Get-EventLog` cmdlet usa o parâmetro **LogName** para especificar o log de eventos do sistema. O parâmetro **Message** especifica uma palavra a ser pesquisada no campo Message de cada evento.

### Exemplo 8: exibir os valores de propriedade de um evento

Este exemplo mostra como exibir todas as propriedades e valores de um evento.

```powershell
$A = Get-EventLog -LogName System -Newest 1
$A | Select-Object -Property *
```

```Output
EventID            : 10016
MachineName        : localhost
Data               : {}
Index              : 13821
Category           : (0)
CategoryNumber     : 0
EntryType          : Error
Message            : The description for Event ID '10016' in Source 'DCOM'...
Source             : DCOM
ReplacementStrings : {Local,...}
InstanceId         : 10016
TimeGenerated      : 1/17/2019 19:17:23
TimeWritten        : 1/17/2019 19:17:23
UserName           : username
Site               :
Container          :
```

O `Get-EventLog` cmdlet usa o parâmetro **LogName** para especificar o log de eventos do sistema. O parâmetro **mais** recente seleciona o objeto de evento mais recente. O objeto é armazenado na `$A` variável. O objeto na `$A` variável é enviado ao pipeline para o `Select-Object` cmdlet.
`Select-Object` usa o parâmetro **Property** com um asterisco ( `*` ) para selecionar todas as propriedades do objeto.

### Exemplo 9: obter eventos de um log de eventos usando uma origem e uma ID de evento

Este exemplo obtém eventos para uma origem especificada e uma ID de evento.

```powershell
Get-EventLog -LogName Application -Source Outlook | Where-Object {$_.EventID -eq 63} |
              Select-Object -Property Source, EventID, InstanceId, Message
```

```Output
Source   EventID   InstanceId   Message
------   -------   ----------   -------
Outlook       63   1073741887   The Exchange web service request succeeded.
Outlook       63   1073741887   Outlook detected a change notification.
Outlook       63   1073741887   The Exchange web service request succeeded.
```

O `Get-EventLog` cmdlet usa o parâmetro **LogName** para especificar o log de eventos do aplicativo. O parâmetro **Source** especifica o nome do aplicativo, Outlook. Os objetos são enviados para o pipeline para o `Where-Object` cmdlet. Para cada objeto no pipeline, o `Where-Object` cmdlet usa a variável `$_.EventID` para comparar a propriedade de ID do evento com o valor especificado. Os objetos são enviados para o pipeline para o `Select-Object` cmdlet. `Select-Object` usa o parâmetro **Property** para selecionar as propriedades a serem exibidas no console do PowerShell.

### Exemplo 10: obter eventos e agrupar por uma propriedade

```powershell
Get-EventLog -LogName System -UserName NT* | Group-Object -Property UserName -NoElement |
              Select-Object -Property Count, Name
```

```Output
Count  Name
-----  ----
6031   NT AUTHORITY\SYSTEM
  42   NT AUTHORITY\LOCAL SERVICE
   4   NT AUTHORITY\NETWORK SERVICE
```

O `Get-EventLog` cmdlet usa o parâmetro **LogName** para especificar o log do sistema. O parâmetro **username** inclui o curinga asterisco ( `*` ) para especificar uma parte do nome de usuário. Os objetos de evento são enviados para o pipeline para o `Group-Object` cmdlet. `Group-Object` usa o parâmetro **Property** para especificar que a propriedade **username** é usada para agrupar os objetos e contar o número de objetos para cada nome de usuário. O parâmetro **NoElement** remove os membros do grupo da saída. Os objetos são enviados para o pipeline para o `Select-Object` cmdlet.
`Select-Object` usa o parâmetro **Property** para selecionar as propriedades a serem exibidas no console do PowerShell.

### Exemplo 11: obter eventos que ocorreram durante um intervalo de data e hora específico

Este exemplo obtém eventos de erro do log de eventos do sistema para um intervalo de data e hora especificado. Os parâmetros **before** e **After** definem o intervalo de data e hora, mas são excluídos da saída.

```powershell
$Begin = Get-Date -Date '1/17/2019 08:00:00'
$End = Get-Date -Date '1/17/2019 17:00:00'
Get-EventLog -LogName System -EntryType Error -After $Begin -Before $End
```

```Output
Index Time          EntryType   Source   InstanceID  Message
----- ----          ---------   ------   ----------  -------
13821 Jan 17 13:40  Error       DCOM          10016  The description for Event ID...
13820 Jan 17 13:11  Error       DCOM          10016  The description for Event ID...
...
12372 Jan 17 10:08  Error       DCOM          10016  The description for Event ID...
12371 Jan 17 09:04  Error       DCOM          10016  The description for Event ID...
```

O `Get-Date` cmdlet usa o parâmetro **Date** para especificar uma data e hora. Os objetos **DateTime** são armazenados nas `$Begin` variáveis e `$End` . O `Get-EventLog` cmdlet usa o parâmetro **LogName** para especificar o log do sistema. O parâmetro **EntryType** especifica o tipo de evento Error. O intervalo de data e hora é definido pelo parâmetro **After** e `$Begin` a variável e o parâmetro **before** e a `$End` variável.

## PARAMETERS

### -Depois de

Obtém os eventos que ocorreram após uma data e hora especificadas. A data e a hora do parâmetro **After** são excluídas da saída. Insira um objeto **DateTime** , como o valor retornado pelo `Get-Date` cmdlet.

```yaml
Type: System.DateTime
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Asbaseobject

Indica que esse cmdlet retorna um objeto **System. Diagnostics. EventLogEntry** padrão para cada evento. Sem esse parâmetro, `Get-EventLog` retorna um objeto **PSObject** estendido com as propriedades **EventLogName** , **Source** e **InstanceId** adicionais.

Para ver o efeito desse parâmetro, redirecione os eventos para o `Get-Member` cmdlet e examine o valor **TypeName** no resultado.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsString

Indica que esse cmdlet retorna a saída como cadeias de caracteres, em vez de objetos.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Antes de

Obtém os eventos que ocorreram antes de uma data e hora especificadas. A data e a hora do parâmetro **before** são excluídas da saída. Insira um objeto **DateTime** , como o valor retornado pelo `Get-Date` cmdlet.

```yaml
Type: System.DateTime
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Esse parâmetro especifica o nome NetBIOS de um computador remoto, endereço IP (Internet Protocol) ou um FQDN (nome de domínio totalmente qualificado).

Se o parâmetro **ComputerName** não for especificado, `Get-EventLog` o padrão será o computador local. O parâmetro também aceita um ponto ( `.` ) para especificar o computador local.

O parâmetro **ComputerName** não depende da comunicação remota do Windows PowerShell. Você pode usar `Get-EventLog` com o parâmetro **ComputerName** mesmo se o computador não estiver configurado para executar comandos remotos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EntryType

Especifica, como uma matriz de cadeia de caracteres, o tipo de entrada dos eventos que esse cmdlet obtém.

Os valores aceitáveis para esse parâmetro são:

- Erro
- Informações
- FailureAudit
- SuccessAudit
- Aviso

```yaml
Type: System.String[]
Parameter Sets: LogName
Aliases: ET
Accepted values: Error, Information, FailureAudit, SuccessAudit, Warning

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Índice

Especifica os valores de índice a serem obtidos do log de eventos. O parâmetro aceita uma cadeia de caracteres separada por vírgulas de valores.

```yaml
Type: System.Int32[]
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceId

Especifica as IDs de instância a serem obtidas do log de eventos. O parâmetro aceita uma cadeia de caracteres separada por vírgulas de valores.

```yaml
Type: System.Int64[]
Parameter Sets: LogName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lista

Exibe a lista de logs de eventos no computador.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogName

Especifica o nome de um log de eventos. Para localizar os nomes de log, use `Get-EventLog -List` . Caracteres curinga são permitidos. Este parâmetro é necessário.

```yaml
Type: System.String
Parameter Sets: LogName
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Mensagem

Especifica uma cadeia de caracteres na mensagem do evento. Você pode usar esse parâmetro para procurar mensagens que contenham determinadas palavras ou frases. Caracteres curinga são permitidos.

```yaml
Type: System.String
Parameter Sets: LogName
Aliases: MSG

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Mais recente

Começa com os eventos mais recentes e Obtém o número especificado de eventos. O número de eventos é necessário, por exemplo `-Newest 100` . Especifica o número máximo de eventos que são retornados.

```yaml
Type: System.Int32
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source

Especifica, como uma matriz de cadeia de caracteres, fontes que foram gravadas no log que esse cmdlet obtém. Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: LogName
Aliases: ABO

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -UserName

Especifica, como uma matriz de cadeia de caracteres, nomes de usuário associados a eventos. Insira nomes ou padrões de nome, como `User01` , `User*` ou `Domain01\User*` . Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

Não é possível canalizar a entrada para `Get-EventLog` .

## SAÍDAS

### System. Diagnostics. EventLogEntry. System. Diagnostics. EventLog. System.String

Se o parâmetro **LogName** for especificado, a saída será uma coleção de objetos **System. Diagnostics. EventLogEntry** .

Se apenas o parâmetro **list** for especificado, a saída será uma coleção de objetos **System. Diagnostics. EventLog** .

Se os parâmetros **list** e **AsString** forem especificados, a saída será uma coleção de objetos **System. String** .

## OBSERVAÇÕES

Os cmdlets `Get-EventLog` e `Get-WinEvent` não têm suporte no ambiente de pré-instalação do Windows (Windows PE).

## LINKS RELACIONADOS

[Clear-EventLog](Clear-EventLog.md)

[Get-WinEvent](../Microsoft.PowerShell.Diagnostics/Get-WinEvent.md)

[Group-Object](../Microsoft.PowerShell.Utility/Group-Object.md)

[Limit-EventLog](Limit-EventLog.md)

[New-EventLog](New-EventLog.md)

[Remove-EventLog](Remove-EventLog.md)

[Select-Object](../Microsoft.PowerShell.Utility/Select-Object.md)

[Show-EventLog](Show-EventLog.md)

[Write-EventLog](Write-EventLog.md)
