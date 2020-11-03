---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 11/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/get-winevent?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WinEvent
ms.openlocfilehash: ba68ded5afe19a98555e7224692ab8dbe09e3486
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193485"
---
# Get-WinEvent

## SINOPSE
Obtém eventos dos logs de evento e dos arquivos de log de rastreamento de eventos em computadores locais e remotos.

## SYNTAX

### GetLogSet (padrão)

```
Get-WinEvent [[-LogName] <String[]>] [-MaxEvents <Int64>] [-ComputerName <String>]
 [-Credential <PSCredential>] [-FilterXPath <String>] [-Force] [-Oldest] [<CommonParameters>]
```

### ListLogSet

```
Get-WinEvent [-ListLog] <String[]> [-ComputerName <String>] [-Credential <PSCredential>] [-Force]
 [<CommonParameters>]
```

### ListProviderSet

```
Get-WinEvent [-ListProvider] <String[]> [-ComputerName <String>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### Getproviderset

```
Get-WinEvent [-ProviderName] <String[]> [-MaxEvents <Int64>] [-ComputerName <String>]
 [-Credential <PSCredential>] [-FilterXPath <String>] [-Force] [-Oldest] [<CommonParameters>]
```

### Fileset

```
Get-WinEvent [-Path] <String[]> [-MaxEvents <Int64>] [-Credential <PSCredential>]
 [-FilterXPath <String>] [-Oldest] [<CommonParameters>]
```

### HashQuerySet

```
Get-WinEvent [-MaxEvents <Int64>] [-ComputerName <String>] [-Credential <PSCredential>]
 [-FilterHashtable] <Hashtable[]> [-Force] [-Oldest] [<CommonParameters>]
```

### Xmlquery

```
Get-WinEvent [-MaxEvents <Int64>] [-ComputerName <String>] [-Credential <PSCredential>]
 [-FilterXml] <XmlDocument> [-Oldest] [<CommonParameters>]
```

## DESCRIPTION

O `Get-WinEvent` cmdlet obtém eventos de logs de eventos, incluindo logs clássicos, como os logs do **sistema** e do **aplicativo** . O cmdlet obtém dados de logs de eventos que são gerados pela tecnologia de log de eventos do Windows introduzida no Windows Vista. E eventos em arquivos de log gerados pelo **ETW (rastreamento de eventos para Windows)** . Por padrão, `Get-WinEvent` o retorna informações de evento na ordem do mais recente para o mais antigo.

`Get-WinEvent` lista logs de eventos e provedores de log de eventos. Para interromper o comando, pressione <kbd>Ctrl</kbd> + <kbd>C</kbd>. Você pode obter eventos de logs selecionados ou de logs gerados por provedores de eventos selecionados. Além disso, você pode combinar eventos de várias fontes em um único comando.
`Get-WinEvent` permite que você filtre eventos usando consultas XPath, consultas XML estruturadas e consultas de tabela de hash.

Se você não estiver executando o PowerShell como administrador, poderá ver mensagens de erro que não podem recuperar informações sobre um log.

## EXEMPLOS

### Exemplo 1: obter todos os logs de um computador local

Esse comando obtém todos os logs de eventos no computador local. Os logs são listados na ordem que os `Get-WinEvent` obtém. Os logs clássicos são recuperados primeiro, seguidos pelos novos logs de eventos do Windows.
É possível que o **RecordCount** de um log seja nulo, que está em branco ou é zero.

```powershell
Get-WinEvent -ListLog *
```

```Output
LogMode   MaximumSizeInBytes RecordCount LogName
-------   ------------------ ----------- -------
Circular            15532032       14500 Application
Circular             1052672         117 Azure Information Protection
Circular             1052672        3015 CxAudioSvcLog
Circular            20971520             ForwardedEvents
Circular            20971520           0 HardwareEvents
```

O `Get-WinEvent` cmdlet obtém informações de log do computador. O parâmetro **listlog** usa o curinga asterisco ( `*` ) para exibir informações sobre cada log.

### Exemplo 2: obter o log de instalação clássico

Esse comando obtém um objeto **EventLogConfiguration** que representa o log de **instalação** clássico. O objeto inclui informações sobre o log, como tamanho do arquivo, provedor, caminho do arquivo e se o log está habilitado.

```powershell
Get-WinEvent -ListLog Setup | Format-List -Property *
```

```Output
FileSize                       : 69632
IsLogFull                      : False
LastAccessTime                 : 3/13/2019 09:41:46
LastWriteTime                  : 3/13/2019 09:41:46
OldestRecordNumber             : 1
RecordCount                    : 23
LogName                        : Setup
LogType                        : Operational
LogIsolation                   : Application
IsEnabled                      : True
IsClassicLog                   : False
SecurityDescriptor             : O:BAG:SYD: ...
LogFilePath                    : %SystemRoot%\System32\Winevt\Logs\Setup.evtx
MaximumSizeInBytes             : 1052672
LogMode                        : Circular
OwningProviderName             : Microsoft-Windows-Eventlog
ProviderNames                  : {Microsoft-Windows-WUSA, Microsoft-Windows-ActionQueue...
ProviderLevel                  :
ProviderKeywords               :
ProviderBufferSize             : 64
ProviderMinimumNumberOfBuffers : 0
ProviderMaximumNumberOfBuffers : 64
ProviderLatency                : 1000
ProviderControlGuid            :
```

O `Get-WinEvent` cmdlet usa o parâmetro **listlog** para especificar o log de **instalação** . O objeto é enviado ao pipeline para o `Format-List` cmdlet. `Format-List` usa o parâmetro **Property** com o curinga asterisco ( `*` ) para exibir cada propriedade.

### Exemplo 3: obter logs de eventos de um servidor

Esse comando só obtém logs de eventos no computador local que contêm eventos. É possível que o **RecordCount** de um log seja nulo ou zero. O exemplo usa a `$_` variável. Para obter mais informações, consulte [about_Automatic_Variables](../Microsoft.PowerShell.Core/about/about_automatic_variables.md).

```powershell
Get-WinEvent -ListLog * -ComputerName localhost | Where-Object { $_.RecordCount }
```

```Output
LogMode   MaximumSizeInBytes RecordCount LogName
-------   ------------------ ----------- -------
Circular            15532032       14546 Application
Circular             1052672         117 Azure Information Protection
Circular             1052672        2990 CxAudioSvcLog
Circular             1052672           9 MSFTVPN Setup
Circular             1052672         282 OAlerts
```

O `Get-WinEvent` cmdlet obtém informações de log do computador. O parâmetro **listlog** usa o curinga asterisco ( `*` ) para exibir informações sobre cada log. O parâmetro **ComputerName** especifica para obter os logs do computador local, **localhost** . Os objetos são enviados para o pipeline para o `Where-Object` cmdlet. `Where-Object` usa `$_.RecordCount` para retornar somente logs que contêm dados. `$_` é uma variável que representa o objeto atual no pipeline. **RecordCount** é uma propriedade do objeto com um valor não nulo.

### Exemplo 4: obter logs de eventos de vários servidores

Este exemplo obtém objetos que representam os logs de eventos do **aplicativo** em três computadores: Server01, Server02 e Server03. A palavra-chave **foreach** é usada porque o parâmetro **ComputerName** aceita apenas um valor. Para obter mais informações, consulte [about_Foreach](../Microsoft.PowerShell.Core/about/about_Foreach.md).

```powershell
$S = 'Server01', 'Server02', 'Server03'
ForEach ($Server in $S) {
  Get-WinEvent -ListLog Application -ComputerName $Server |
    Select-Object LogMode, MaximumSizeInBytes, RecordCount, LogName,
      @{name='ComputerName'; expression={$Server}} |
    Format-Table -AutoSize
}
```

```Output
 LogMode MaximumSizeInBytes RecordCount LogName     ComputerName
 ------- ------------------ ----------- -------     ------------
Circular           15532032       14577 Application Server01
Circular           15532032        9689 Application Server02
Circular           15532032        5309 Application Server03
```

A variável `$S` armazena os nomes três servidores: **Server01** , **Server02** e **Server03** . A instrução **foreach** usa um loop para processar cada servidor, `($Server in $S)` . O bloco de script nas chaves ( `{ }` ) executa o `Get-WinEvent` comando. O parâmetro **listlog** especifica o log do **aplicativo** . O parâmetro **ComputerName** usa a variável `$Server` para obter informações de log de cada servidor.

Os objetos são enviados para o pipeline para o `Select-Object` cmdlet. `Select-Object` Obtém as propriedades **LogMode** , **MaximumSizeInBytes** , **RecordCount** , **LogName** e usa uma expressão calculada para exibir o **ComputerName** usando a `$Server` variável. Os objetos são enviados ao pipeline para o `Format-Table` cmdlet para exibir a saída no console do PowerShell. O parâmetro **AutoSize** formata a saída para se ajustar à tela.

### Exemplo 5: obter provedores de log de eventos e nomes de log

Esse comando obtém os provedores de log de eventos e os logs para os quais eles gravam.

```powershell
Get-WinEvent -ListProvider *
```

```Output
Name     : .NET Runtime
LogLinks : {Application}
Opcodes  : {}
Tasks    : {}

Name     : .NET Runtime Optimization Service
LogLinks : {Application}
Opcodes  : {}
Tasks    : {}
```

O `Get-WinEvent` cmdlet obtém informações de log do computador. O parâmetro **listprovider** usa o curinga asterisco ( `*` ) para exibir informações sobre cada provedor. Na saída, o **nome** é o provedor e **LogLinks** é o log no qual o provedor grava.

### Exemplo 6: obter todos os provedores de log de eventos que gravam em um log específico

Esse comando obtém todos os provedores que gravam no log do **aplicativo** .

```powershell
(Get-WinEvent -ListLog Application).ProviderNames
```

```Output
.NET Runtime
.NET Runtime Optimization Service
Application
Application Error
Application Hang
Application Management
```

O `Get-WinEvent` cmdlet obtém informações de log do computador. O parâmetro **listlog** usa o **aplicativo** para obter objetos para esse log. Osnames do **provedor** são uma propriedade do objeto e exibe os provedores que gravam no log do **aplicativo** .

### Exemplo 7: obter nomes de provedor de log de eventos que contêm uma cadeia de caracteres específica

Esse comando obtém os provedores de log de eventos com nomes que incluem uma cadeia de caracteres específica no nome do provedor.

```powershell
Get-WinEvent -ListProvider *Policy*
```

```Output
Name     : Group Policy Applications
LogLinks : {Application}
Opcodes  : {}
Tasks    : {}

Name     : Group Policy Client
LogLinks : {Application}
Opcodes  : {}
Tasks    : {}

Name     : Group Policy Data Sources
LogLinks : {Application}
Opcodes  : {}
Tasks    : {}
```

O `Get-WinEvent` cmdlet obtém informações de log do computador. O parâmetro **listprovider** usa o curinga asterisco ( `*` ) para encontrar a **política** em qualquer lugar dentro do nome do provedor.

### Exemplo 8: obter IDs de evento que o provedor de eventos gera

Esse comando lista as IDs de eventos que o provedor de eventos **Microsoft-Windows-GroupPolicy** gera junto com a descrição do evento.

```powershell
(Get-WinEvent -ListProvider Microsoft-Windows-GroupPolicy).Events | Format-Table Id, Description
```

```Output
  Id  Description
  --  -----------
1500  The Group Policy settings for the computer were processed successfully...
1501  The Group Policy settings for the user were processed successfully...
4115  Group Policy Service started.
4116  Started the Group Policy service initialization phase.
4117  Group Policy Session started.
```

O `Get-WinEvent` cmdlet obtém informações de log do computador. O parâmetro **listprovider** especifica o provedor, **Microsoft-Windows-GroupPolicy** . A expressão é encapsulada entre parênteses e usa a propriedade **Events** para obter objetos. Os objetos são enviados para o pipeline para o `Format-Table` cmdlet. `Format-Table` exibe a **ID** e a **Descrição** dos objetos de evento.

### Exemplo 9: obter informações de log das propriedades do objeto de evento

Este exemplo mostra como obter informações sobre o conteúdo de um log usando as propriedades do objeto de evento.
Os objetos de evento são armazenados em uma variável e, em seguida, agrupados e contados por ID e **nível** do **evento** .

```powershell
$Event = Get-WinEvent -LogName 'Windows PowerShell'
$Event.Count
$Event | Group-Object -Property Id -NoElement | Sort-Object -Property Count -Descending
$Event | Group-Object -Property LevelDisplayName -NoElement
```

```Output
195

Count  Name
-----  ----
  147  600
   22  400
   21  601
    3  403
    2  103

Count  Name
-----  ----
    2  Warning
  193  Information
```

O `Get-WinEvent` cmdlet usa o parâmetro **LogName** para especificar o log de eventos do **Windows PowerShell** . Os objetos de evento são armazenados na `$Event` variável. A propriedade **Count** de `$Event` mostra o número total de eventos registrados.

A `$Event` variável é enviada ao pipeline para o `Group-Object` cmdlet. `Group-Object` usa o parâmetro **Property** para especificar a propriedade **ID** e conta os objetos pelo valor da ID do evento. O parâmetro **NoElement** remove outras propriedades da saída de objetos. Os objetos agrupados são enviados ao pipeline para o `Sort-Object` cmdlet. `Sort-Object` usa o parâmetro **Property** para classificar os objetos por **contagem** . O parâmetro **decrescente** exibe a saída por contagem, do mais alto ao mais baixo. Na saída, a coluna **Count** contém o número total de cada evento. A coluna **nome** contém os números de identificação do evento agrupado.

A `$Event` variável é enviada ao pipeline para o `Group-Object` cmdlet. `Group-Object` usa o parâmetro **Property** para especificar a propriedade **LevelDisplayName** e conta os objetos por **LevelDisplayName** . Os objetos são agrupados pelos níveis, como **aviso** e **informações** .
O parâmetro **NoElement** remove outras propriedades da saída. Na saída, a coluna **Count** contém o número total de cada evento. A coluna **nome** contém o **LevelDisplayName** agrupado.

### Exemplo 10: obter eventos de erro que têm uma cadeia de caracteres especificada em seu nome

Este exemplo usa uma cadeia de caracteres separada por vírgulas de nomes de log. A saída é agrupada pelo nível, como erro ou aviso e o nome do log.

```powershell
Get-WinEvent -LogName *PowerShell*, Microsoft-Windows-Kernel-WHEA* |
  Group-Object -Property LevelDisplayName, LogName -NoElement |
    Format-Table -AutoSize
```

```Output
Count  Name
-----  ----
    1  Error, PowerShellCore/Operational
   26  Information, Microsoft-Windows-Kernel-WHEA/Operational
  488  Information, Microsoft-Windows-PowerShell/Operational
   77  Information, PowerShellCore/Operational
 9835  Information, Windows PowerShell
   19  Verbose, PowerShellCore/Operational
  444  Warning, Microsoft-Windows-PowerShell/Operational
  512  Warning, PowerShellCore/Operational
```

O `Get-WinEvent` cmdlet obtém informações de log do computador. O parâmetro **LogName** usa uma cadeia de caracteres separada por vírgulas com o curinga asterisco ( `*` ) para especificar os nomes de log. Os objetos são enviados para o pipeline para o `Group-Object` cmdlet. `Group-Object` usa o parâmetro **Property** para agrupar os objetos por **LevelDisplayName** e **LogName** . O parâmetro **NoElement** remove outras propriedades da saída. Os objetos agrupados são enviados ao pipeline para o `Format-Table` cmdlet. `Format-Table` usa o parâmetro **AutoSize** para formatar as colunas. A coluna **Count** contém o número total de cada evento. A coluna **Name** contém o **LevelDisplayName** e o **LogName** agrupados.

### Exemplo 11: obter eventos de um log de eventos arquivados

`Get-WinEvent` pode obter informações de eventos de arquivos de log salvos. Este exemplo usa um log do PowerShell arquivado armazenado no computador local.

```powershell
Get-WinEvent -Path 'C:\Test\Windows PowerShell.evtx'
```

```Output
   ProviderName: PowerShell

TimeCreated              Id LevelDisplayName  Message
-----------              -- ----------------  -------
3/15/2019 13:54:13      403 Information       Engine state is changed from Available to Stopped...
3/15/2019 13:54:13      400 Information       Engine state is changed from None to Available...
3/15/2019 13:54:13      600 Information       Provider "Variable" is Started...
3/15/2019 13:54:13      600 Information       Provider "Function" is Started...
3/15/2019 13:54:13      600 Information       Provider "FileSystem" is Started...
```

O `Get-WinEvent` cmdlet obtém informações de log do computador. O parâmetro **path** especifica o diretório e o nome do arquivo.

### Exemplo 12: obter um número específico de eventos de um log de eventos Arquivado

Esses comandos obtêm um número específico de eventos de um log de eventos arquivados. `Get-WinEvent` tem parâmetros que podem obter um número máximo de eventos ou os eventos mais antigos. Este exemplo usa um log do PowerShell arquivado armazenado em **C:\Test\PowerShellCore Operational. evtx** .

```powershell
Get-WinEvent -Path 'C:\Test\PowerShellCore Operational.evtx' -MaxEvents 100
```

```Output
   ProviderName: PowerShellCore

TimeCreated                 Id   LevelDisplayName  Message
-----------                 --   ----------------  -------
3/15/2019 09:54:54        4104   Warning           Creating Scriptblock text (1 of 1):...
3/15/2019 09:37:13       40962   Information       PowerShell console is ready for user input
3/15/2019 07:56:24        4104   Warning           Creating Scriptblock text (1 of 1):...
...
3/7/2019 10:53:22        40961   Information       PowerShell console is starting up
3/7/2019 10:53:22         8197   Verbose           Runspace state changed to Opening
3/7/2019 10:53:22         8195   Verbose           Opening RunspacePool
```

O `Get-WinEvent` cmdlet obtém informações de log do computador. O parâmetro **path** especifica o diretório e o nome do arquivo. O parâmetro **MaxEvents** especifica que 100 registros são exibidos, do mais recente ao mais antigo.

### Exemplo 13: rastreamento de eventos para Windows

O ETW (rastreamento de eventos para Windows) grava eventos no log à medida que os eventos ocorrem. Os eventos são armazenados na ordem do mais antigo para o mais recente. Um arquivo ETW arquivado é salvo como um `.etl` **TraceLog. etl** .
Os eventos são listados na ordem em que são gravados no log, portanto, o parâmetro *mais antigo* é necessário.

```powershell
Get-WinEvent -Path 'C:\Tracing\TraceLog.etl' -Oldest |
  Sort-Object -Property TimeCreated -Descending |
    Select-Object -First 100
```

O `Get-WinEvent` cmdlet obtém informações de log do arquivo arquivado. O parâmetro **path** especifica o diretório e o nome do arquivo. O parâmetro **mais antigo** é usado para gerar eventos na ordem em que são gravados, mais antigo para o mais recente. Os objetos são enviados ao pipeline para o `Sort-Object` cmdlet `Sort-Object` , classifica os objetos em ordem decrescente pelo valor da propriedade **timecreateed** . Os objetos são enviados para o pipeline para o `Select-Object` cmdlet que exibe os eventos mais recentes do 100.

### Exemplo 14: obter eventos de um log de rastreamento de eventos

Este exemplo mostra como obter os eventos de um arquivo de log de rastreamento de eventos ( `.etl` ) e um arquivo de log do Windows PowerShell arquivado ( `.evtx` ). Você pode combinar vários tipos de arquivo em um único comando.
Como os arquivos contêm o mesmo tipo de **.NET Framework** objeto, **EventLogRecord** , você pode filtrá-los com as mesmas propriedades. O comando requer o parâmetro **mais antigo** porque ele está lendo de um `.etl` arquivo, mas o parâmetro **mais antigo** se aplica a cada arquivo.

```powershell
Get-WinEvent -Path 'C:\Tracing\TraceLog.etl', 'C:\Test\Windows PowerShell.evtx' -Oldest |
  Where-Object { $_.Id -eq '403' }
```

O `Get-WinEvent` cmdlet obtém informações de log dos arquivos mortos. O parâmetro **path** usa uma lista separada por vírgulas para especificar cada diretório de arquivos e nome de arquivo. O parâmetro **mais antigo** é usado para gerar eventos na ordem em que são gravados, mais antigo para o mais recente. Os objetos são enviados para o pipeline para o `Where-Object` cmdlet. `Where-Object` usa um bloco de script para localizar eventos com e **ID** de **403** . A `$_` variável representa o objeto atual no pipeline e **ID** é a propriedade de ID do evento.

### Exemplo 15: filtrar resultados do log de eventos

Este exemplo mostra uma variedade de métodos para filtrar e selecionar eventos de um log de eventos. Todos esses comandos obtêm eventos que ocorreram nas últimas 24 horas do log de eventos do **Windows PowerShell** .
Os métodos de filtro são mais eficientes do que usar o `Where-Object` cmdlet. Os filtros são aplicados à medida que os objetos são recuperados. `Where-Object` Recupera todos os objetos e aplica filtros a todos os objetos.

```powershell
# Using the Where-Object cmdlet:
$Yesterday = (Get-Date) - (New-TimeSpan -Day 1)
Get-WinEvent -LogName 'Windows PowerShell' | Where-Object { $_.TimeCreated -ge $Yesterday }

# Using the FilterHashtable parameter:
$Yesterday = (Get-Date) - (New-TimeSpan -Day 1)
Get-WinEvent -FilterHashtable @{ LogName='Windows PowerShell'; Level=3; StartTime=$Yesterday }

# Using the FilterXML parameter:
$xmlQuery = @'
<QueryList>
  <Query Id="0" Path="Windows PowerShell">
    <Select Path="System">*[System[(Level=3) and
        TimeCreated[timediff(@SystemTime) &lt;= 86400000]]]</Select>
  </Query>
</QueryList>
'@
Get-WinEvent -FilterXML $xmlQuery

# Using the FilterXPath parameter:
$XPath = '*[System[Level=3 and TimeCreated[timediff(@SystemTime) &lt;= 86400000]]]'
Get-WinEvent -LogName 'Windows PowerShell' -FilterXPath $XPath
```

### Exemplo 16: usar FilterHashtable para obter eventos do log do aplicativo

Este exemplo usa o parâmetro **FilterHashTable** para obter eventos do log do **aplicativo** . A tabela de hash usa pares de **chave/valor** . Para obter mais informações sobre o parâmetro **FilterHashTable** , consulte [criando consultas de Get-WinEvent com FilterHashTable](/powershell/scripting/samples/Creating-Get-WinEvent-queries-with-FilterHashtable).
Para obter informações sobre tabelas de hash, confira [about_Hash_Tables](../Microsoft.PowerShell.Core/about/about_hash_tables.md).

```powershell
$Date = (Get-Date).AddDays(-2)
Get-WinEvent -FilterHashtable @{ LogName='Application'; StartTime=$Date; Id='1003' }
```

O `Get-Date` cmdlet usa o método **AddDays** para obter uma data que seja de dois dias antes da data atual. O objeto Date é armazenado na `$Date` variável.

O `Get-WinEvent` cmdlet obtém informações de log. O parâmetro **FilterHashTable** é usado para filtrar a saída. A chave **LogName** especifica o valor como o log do **aplicativo** . A chave **StartTime** usa o valor armazenado na `$Date` variável. A chave de **ID** usa um valor de ID de evento, **1003** .

### Exemplo 17: usar FilterHashtable para obter erros de aplicativo

Este exemplo usa o parâmetro **FilterHashTable** para encontrar erros de aplicativo do Internet Explorer que ocorreram na última semana.

```powershell
$StartTime = (Get-Date).AddDays(-7)
Get-WinEvent -FilterHashtable @{
  Logname='Application'
  ProviderName='Application Error'
  Data='iexplore.exe'
  StartTime=$StartTime
}
```

O `Get-Date` cmdlet usa o método **AddDays** para obter uma data que seja de sete dias antes da data atual. O objeto Date é armazenado na `$StartTime` variável.

O `Get-WinEvent` cmdlet obtém informações de log. O parâmetro **FilterHashTable** é usado para filtrar a saída. A chave **LogName** especifica o valor como o log do **aplicativo** . A chave **ProviderName** usa o valor, **erro de aplicativo** , que é a **origem** do evento. A chave de **dados** usa o valor **iexplore.exe** chave **StartTime** usa o valor armazenado em `$StartTime` variável.

## PARAMETERS

### -ComputerName

Especifica o nome do computador em que este cmdlet obtém eventos dos logs de eventos. Digite o nome NetBIOS, um endereço IP ou o FQDN (nome de domínio totalmente qualificado) do computador. O valor padrão é o computador local, **localhost** . Esse parâmetro aceita apenas um nome de computador por vez.

Para obter logs de eventos de computadores remotos, configure a porta do firewall para o serviço log de eventos para permitir o acesso remoto.

Esse cmdlet não depende da comunicação remota do PowerShell. Você pode usar o parâmetro **ComputerName** , mesmo que seu computador não esteja configurado para executar comandos remotos.

```yaml
Type: System.String
Parameter Sets: GetLogSet, ListLogSet, ListProviderSet, GetProviderSet, HashQuerySet, XmlQuerySet
Aliases: Cn

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Especifica uma conta de usuário que tem permissão para executar esta ação. O valor padrão é o usuário atual.

Digite um nome de usuário, como **User01** ou **Domínio01 \ Usuário01** . Ou insira um objeto **PSCredential** , como um gerado pelo `Get-Credential` cmdlet. Se você digitar um nome de usuário, uma senha será solicitada. Se você digitar apenas o nome do parâmetro, será solicitado que você forneça um nome de usuário e uma senha.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilterHashtable

Especifica uma consulta no formato de tabela de hash para selecionar eventos de um ou mais logs de eventos. A consulta contém uma tabela de hash com um ou mais pares **chave/valor** .

Consultas de tabela de hash têm as seguintes regras:

- Chaves e valores não diferenciam maiúsculas de minúsculas.
- Os caracteres curinga são válidos somente nos valores associados às chaves **LogName** e **ProviderName** .
- Cada chave pode ser listada apenas uma vez em cada tabela de hash.
- O valor do **caminho** usa caminhos `.etl` para `.evt` arquivos de `.evtx` log, e.
- As chaves **LogName** , **Path** e **ProviderName** podem ser usadas na mesma consulta.
- A chave **userid** pode usar um SID (identificador de segurança) válido ou um nome de conta de domínio que possa ser usado para construir um **objeto System. Security. principal. NTAccount** válido.
- O valor dos **dados** usa dados de evento em um campo sem nome. Por exemplo, eventos em logs de eventos clássicos.

Quando `Get-WinEvent` o não pode interpretar um par **chave/valor** , ele interpreta a chave como um nome que diferencia maiúsculas de minúsculas para os dados do evento no evento.

Os pares de `Get-WinEvent` **chave/valor** válidos são os seguintes:

- **LogName**=`<String[]>`
- **ProviderName**=`<String[]>`
- **Multi-Path**=`<String[]>`
- **Palavras-chave**=`<Long[]>`
- **SESSÃO**=`<Int32[]>`
- **Geral**=`<Int32[]>`
- **StartTime**=`<DateTime>`
- **Final**=`<DateTime>`
- **ID**=`<SID>`
- **Dado**=`<String[]>`

```yaml
Type: System.Collections.Hashtable[]
Parameter Sets: HashQuerySet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilterXPath

Especifica uma consulta XPath que esse cmdlet seleciona eventos de um ou mais logs.

Para obter mais informações sobre a linguagem XPath, consulte [referência de XPath](/previous-versions/dotnet/netframework-4.0/ms256115(v=vs.100)) e a seção filtros de seleção da seleção de [eventos](/previous-versions/aa385231(v=vs.85)).

```yaml
Type: System.String
Parameter Sets: GetLogSet, GetProviderSet, FileSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilterXml

Especifica uma consulta XML estruturada que esse cmdlet seleciona eventos de um ou mais logs de eventos.

Para gerar uma consulta XML válida, use os recursos **criar exibição personalizada** e **Filtrar log atual** no Windows visualizador de eventos. Use os itens na caixa de diálogo para criar uma consulta e, em seguida, clique na guia XML para exibir a consulta em formato XML. Você pode copiar o XML da guia XML para o valor do parâmetro **FilterXml** . Para obter mais informações sobre os recursos do Visualizador de Eventos, consulte a Ajuda do Visualizador de Eventos.

Use uma consulta XML para criar uma consulta complexa que contenha várias instruções XPath. O formato XML também permite que você use um elemento **XML de supressão** que exclui eventos da consulta. Para obter mais informações sobre o esquema XML para consultas de log de eventos, consulte [esquema de consulta](/windows/win32/wes/queryschema-schema) e a seção consultas de eventos XML da [seleção de eventos](/previous-versions/aa385231(v=vs.85)).

```yaml
Type: System.Xml.XmlDocument
Parameter Sets: XmlQuerySet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Obtém logs analíticos e de depuração, além de outros logs de eventos. O parâmetro **Force** é necessário para obter um log de depuração ou analítico quando o valor do parâmetro de nome incluir caracteres curinga.

Por padrão, o `Get-WinEvent` cmdlet exclui esses logs, a menos que você especifique o nome completo de um log analítico ou de depuração.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GetLogSet, ListLogSet, GetProviderSet, HashQuerySet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ListLog

Especifica os logs de evento. Digite os nomes de log de eventos em uma lista separada por vírgulas. Caracteres curinga são permitidos. Para obter todos os logs, use o curinga asterisco ( `*` ).

```yaml
Type: System.String[]
Parameter Sets: ListLogSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Listprovider

Especifica os provedores de log de eventos que esse cmdlet obtém. Um provedor de log de eventos é um programa ou serviço que grava eventos no log de eventos.

Digite os nomes de provedor em uma lista separada por vírgulas. Caracteres curinga são permitidos. Para obter os provedores de todos os logs de eventos no computador, use o curinga asterisco ( `*` ).

```yaml
Type: System.String[]
Parameter Sets: ListProviderSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -LogName

Especifica os logs de eventos dos quais este cmdlet obtém eventos. Digite os nomes de log de eventos em uma lista separada por vírgulas. Caracteres curinga são permitidos. Você também pode canalizar nomes de log para o `Get-WinEvent` cmdlet.

> [!NOTE]
> O PowerShell não limita a quantidade de logs que você pode solicitar. No entanto, o `Get-WinEvent` cmdlet consulta a API do Windows que tem um limite de 256. Isso pode dificultar o filtro por todos os seus logs ao mesmo tempo. Você pode contornar isso usando um `foreach` loop para iterar em cada log como este: `Get-WinEvent -ListLog * | ForEach-Object{ Get-WinEvent -LogName $_.Logname }`

```yaml
Type: System.String[]
Parameter Sets: GetLogSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -MaxEvents

Especifica o número máximo de eventos que são retornados. Insira um número inteiro, como 100. O padrão é retornar todos os eventos em logs ou arquivos.

```yaml
Type: System.Int64
Parameter Sets: GetLogSet, GetProviderSet, FileSet, HashQuerySet, XmlQuerySet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mais antigo

Indique que esse cmdlet obtém os eventos na ordem mais antiga primeiro. Por padrão, os eventos são retornados na ordem do mais recente primeiro.

Esse parâmetro é necessário para obter eventos de `.etl` e `.evt` arquivos e de logs analíticos e de depuração. Nesses arquivos, eventos são registrados na ordem do mais antigo primeiro e os eventos podem ser retornados apenas na ordem do mais antigo primeiro.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GetLogSet, GetProviderSet, FileSet, HashQuerySet, XmlQuerySet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Especifica o caminho para os arquivos de log de eventos dos quais esse cmdlet obtém eventos. Digite os caminhos para os arquivos de log em uma lista separada por vírgulas ou use caracteres curinga para criar padrões de caminho de arquivo.

`Get-WinEvent` dá suporte a arquivos com as `.evt` `.evtx` extensões de nome de arquivo, e `.etl` . Você pode incluir eventos de diferentes arquivos e tipos de arquivo no mesmo comando.

```yaml
Type: System.String[]
Parameter Sets: FileSet
Aliases: PSPath

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -ProviderName

Especifica, como uma matriz de cadeia de caracteres, os provedores de log de eventos dos quais esse cmdlet obtém eventos. Digite os nomes de provedor em uma lista separada por vírgulas ou use caracteres curinga para criar padrões de nome de provedor.

Um provedor de log de eventos é um programa ou serviço que grava eventos no log de eventos. Não é um provedor do PowerShell.

```yaml
Type: System.String[]
Parameter Sets: GetProviderSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. String, System.Xml.Xmldocumento, System. Collections. Hashtable

Você pode canalizar um **LogName** (cadeia de caracteres), uma consulta **FilterXML** ou uma consulta **FilterHashTable** para `Get-WinEvent` .

## SAÍDAS

### System. Diagnostics. Eventing. Reader. EventLogConfiguration, System. Diagnostics. Eventing. Reader. EventLogRecord, System. Diagnostics. Eventing. Reader. ProviderMetadata

Com o parâmetro **listlog** , `Get-WinEvent` retorna objetos **System. Diagnostics. Eventing. Reader. EventLogConfiguration** .

Com o parâmetro **listprovider** , `Get-WinEvent` retorna objetos **System. Diagnostics. Eventing. Reader. ProviderMetadata** .

Com todos os outros parâmetros, `Get-WinEvent` retorna objetos **System. Diagnostics. Eventing. Reader. EventLogRecord** .

## OBSERVAÇÕES

`Get-WinEvent` o é projetado para substituir o `Get-EventLog` cmdlet em computadores que executam o Windows Vista e versões posteriores do Windows. `Get-EventLog` Obtém eventos somente em logs de eventos clássicos. `Get-EventLog` é mantido para compatibilidade com versões anteriores.

`Get-WinEvent` `Get-EventLog` Não há suporte para os cmdlets e no ambiente de pré-instalação do Windows (Windows PE).

## LINKS RELACIONADOS

[about_Automatic_Variables](../Microsoft.PowerShell.Core/about/about_automatic_variables.md)

[about_Foreach](../Microsoft.PowerShell.Core/about/about_Foreach.md)

[about_Hash_Tables](../Microsoft.PowerShell.Core/about/about_hash_tables.md)

[Criando consultas Get-WinEvent com FilterHashtable](/powershell/scripting/samples/Creating-Get-WinEvent-queries-with-FilterHashtable)

[Format-Table](../Microsoft.PowerShell.Utility/Format-Table.md)

[Group-Object](../Microsoft.PowerShell.Utility/Group-Object.md)

[Sort-Object](../Microsoft.PowerShell.Utility/Sort-Object.md)

[Where-Object](../Microsoft.PowerShell.Core/Where-Object.md)
