---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 11/06/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/get-counter?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Counter
ms.openlocfilehash: b8b78c0a2dec0c3e51c91df522cc5b026952a222
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194739"
---
# Get-Counter

## SINOPSE
Obtém os dados do contador de desempenho de computadores locais e remotos.

## SYNTAX

### Getcounterset (padrão)

```
Get-Counter [[-Counter] <String[]>] [-SampleInterval <Int32>] [-MaxSamples <Int64>] [-Continuous]
 [-ComputerName <String[]>] [<CommonParameters>]
```

### ListSetSet

```
Get-Counter [-ListSet] <String[]> [-ComputerName <String[]>] [<CommonParameters>]
```

## DESCRIPTION

O `Get-Counter` cmdlet obtém dados do contador de desempenho diretamente da instrumentação de monitoramento de desempenho na família de sistemas operacionais Windows. `Get-Counter` Obtém dados de desempenho de um computador local ou de computadores remotos.

Você pode usar os `Get-Counter` parâmetros para especificar um ou mais computadores, listar os conjuntos de contadores de desempenho e as instâncias que eles contêm, definir os intervalos de exemplo e especificar o número máximo de amostras. Sem parâmetros, `Get-Counter` obtém dados do contador de desempenho para um conjunto de contadores do sistema.

Muitos conjuntos de contadores são protegidos por listas de controle de acesso (ACL). Para ver todos os conjuntos de contadores, abra o PowerShell com a opção **Executar como administrador** .

Esse cmdlet foi reintroduzido no PowerShell 7.

## EXEMPLOS

### Exemplo 1: obter a lista de conjuntos de contadores

Este exemplo obtém a lista de conjuntos de contadores do computador local.

```powershell
Get-Counter -ListSet *
```

```Output
CounterSetName     : Processor
MachineName        : .
CounterSetType     : MultiInstance
Description        : The Processor performance object consists of counters that measure aspects ...
                     computer that performs arithmetic and logical computations, initiates ...
                     computer can have multiple processors.  The processor object represents ...
Paths              : {\Processor(*)\% Processor Time, \Processor(*)\% User Time, ...
PathsWithInstances : {\Processor(0)\% Processor Time, \Processor(1)\% Processor Time, ...
Counter            : {\Processor(*)\% Processor Time, \Processor(*)\% User Time, ...
```

`Get-Counter` usa o parâmetro **ListSet** com um asterisco ( `*` ) para obter a lista de conjuntos de contadores.
O ponto ( `.` ) na coluna **MachineName** representa o computador local.

### Exemplo 2: especificar SampleInterval e MaxSamples

Este exemplo obtém os dados do contador para todos os processadores no computador local. Os dados são coletados em intervalos de dois segundos até que haja três amostras.

```powershell
Get-Counter -Counter "\Processor(_Total)\% Processor Time" -SampleInterval 2 -MaxSamples 3
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/18/2019 14:39:56        \\Computer01\processor(_total)\% processor time :
                          20.7144271584086

6/18/2019 14:39:58        \\Computer01\processor(_total)\% processor time :
                          10.4391790575511

6/18/2019 14:40:01        \\Computer01\processor(_total)\% processor time :
                          37.5968799396998
```

`Get-Counter` usa o parâmetro **Counter** para especificar o caminho do contador `\Processor(_Total)\% Processor Time` . O parâmetro **SampleInterval** define um intervalo de dois segundos para verificar o contador. **MaxSamples** determina que três é o número máximo de vezes para verificar o contador.

### Exemplo 3: obter amostras contínuas de um contador

Este exemplo obtém amostras contínuas para um contador a cada segundo. Para interromper o comando, pressione <kbd>Ctrl</kbd> + <kbd>C</kbd>. Para especificar um intervalo mais longo entre amostras, use o parâmetro **SampleInterval** .

```powershell
Get-Counter -Counter "\Processor(_Total)\% Processor Time" -Continuous
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/19/2019 15:35:03        \\Computer01\processor(_total)\% processor time :
                          43.8522842937022

6/19/2019 15:35:04        \\Computer01\processor(_total)\% processor time :
                          29.7896844697383

6/19/2019 15:35:05        \\Computer01\processor(_total)\% processor time :
                          29.4962645638135

6/19/2019 15:35:06        \\Computer01\processor(_total)\% processor time :
                          25.5901500127408
```

`Get-Counter` usa o parâmetro **Counter** para especificar o `\Processor\% Processor Time` contador.
O parâmetro **Continuous** especifica para obter amostras a cada segundo até que o comando seja interrompido com <kbd>Ctrl</kbd> + <kbd>C</kbd>.

### Exemplo 4: lista alfabética de conjuntos de contadores

Este exemplo usa o pipeline para obter a lista de contadores definida e, em seguida, classificar a lista em ordem alfabética.

```powershell
Get-Counter -ListSet * |
  Sort-Object -Property CounterSetName |
    Format-Table CounterSetName, CounterSetType -AutoSize
```

```Output
CounterSetName                        CounterSetType
--------------                        --------------
.NET CLR Data                         SingleInstance
.NET Data Provider for SqlServer      SingleInstance
AppV Client Streamed Data Percentage  SingleInstance
Authorization Manager Applications    SingleInstance
BitLocker                             MultiInstance
Bluetooth Device                      SingleInstance
Cache                                 SingleInstance
Client Side Caching                   SingleInstance
```

`Get-Counter` usa o parâmetro **ListSet** com um asterisco ( `*` ) para obter uma lista completa de conjuntos de contadores. Os objetos **CounterSet** são enviados pelo pipeline. `Sort-Object` usa o parâmetro **Property** para especificar que os objetos são classificados por **CounterSetName** . Os objetos são enviados ao pipeline para `Format-Table` . O parâmetro **AutoSize** ajusta as larguras das colunas para minimizar o truncamento.

O ponto ( `.` ) na coluna **MachineName** representa o computador local.

### Exemplo 5: executar um trabalho em segundo plano para obter dados do contador

Neste exemplo, `Start-Job` executa um `Get-Counter` comando como um trabalho em segundo plano no computador local.
Para exibir a saída do contador de desempenho do trabalho, use o `Receive-Job` cmdlet.

```powershell
Start-Job -ScriptBlock {Get-Counter -Counter "\LogicalDisk(_Total)\% Free Space" -MaxSamples 1000}
```

```Output
Id     Name  PSJobTypeName   State    HasMoreData  Location   Command
--     ----  -------------   -----    -----------  --------   -------
1      Job1  BackgroundJob   Running  True         localhost  Get-Counter -Counter
```

`Start-Job` usa o parâmetro **scriptblock** para executar um `Get-Counter` comando. `Get-Counter` usa o parâmetro **Counter** para especificar o caminho do contador `\LogicalDisk(_Total)\% Free Space` . O parâmetro **MaxSamples** especifica a obtenção de exemplos de 1000 do contador.

### Exemplo 6: obter dados do contador de vários computadores

Este exemplo usa uma variável para obter dados do contador de desempenho de dois computadores.

```powershell
$DiskReads = "\LogicalDisk(C:)\Disk Reads/sec"
$DiskReads | Get-Counter -ComputerName Server01, Server02 -MaxSamples 10
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/21/2019 10:51:04        \\Server01\logicaldisk(c:)\disk reads/sec :
                          0

                          \\Server02\logicaldisk(c:)\disk reads/sec :
                          0.983050344269146
```

A `$DiskReads` variável armazena o `\LogicalDisk(C:)\Disk Reads/sec` caminho do contador. A `$DiskReads` variável é enviada ao pipeline para `Get-Counter` . **Counter** é o primeiro parâmetro de posição e aceita o caminho armazenado em `$DiskReads` . **ComputerName** especifica os dois computadores e **MaxSamples** especifica para obter 10 amostras de cada computador.

### Exemplo 7: obter os valores de instância de um contador de vários computadores aleatórios

Este exemplo obtém o valor de um contador de desempenho em 50 computadores remotos aleatórios na empresa. O parâmetro **ComputerName** usa nomes de computador aleatórios armazenados em uma variável. Para atualizar os nomes dos computadores na variável, recrie a variável.

Uma alternativa para os nomes de servidor no parâmetro **ComputerName** é usar um arquivo de texto. Por exemplo:

`-ComputerName (Get-Random (Get-Content -Path C:\Servers.txt) -Count 50)`

O caminho do contador inclui um asterisco ( `*` ) no nome da instância para obter os dados para cada um dos processadores do computador remoto.

```powershell
$Servers = Get-Random (Get-Content -Path C:\Servers.txt) -Count 50
$Counter = "\Processor(*)\% Processor Time"
Get-Counter -Counter $Counter -ComputerName $Servers
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/20/2019 12:20:35        \\Server01\processor(0)\% processor time :
                          6.52610319637854

                          \\Server01\processor(1)\% processor time :
                          3.41030663625782

                          \\Server01\processor(2)\% processor time :
                          9.64189975649925

                          \\Server01\processor(3)\% processor time :
                          1.85240835619747

                          \\Server01\processor(_total)\% processor time :
                          5.35768447160776
```

O `Get-Random` cmdlet usa `Get-Content` para selecionar 50 nomes de computador aleatórios do `Servers.txt` arquivo. Os nomes dos computadores remotos são armazenados na `$Servers` variável. O `\Processor(*)\% Processor Time` caminho do contador é armazenado na `$Counter` variável. `Get-Counter` usa o parâmetro **Counter** para especificar os contadores na `$Counter` variável. O parâmetro **ComputerName** especifica os nomes de computador na `$Servers` variável.

### Exemplo 8: usar a propriedade Path para obter nomes de caminho formatados

Este exemplo usa a propriedade **path** de um conjunto de contadores para localizar os nomes de caminho formatados para os contadores de desempenho.

O pipeline é usado com o `Where-Object` cmdlet para localizar um subconjunto dos nomes de caminho. Para localizar um contador define uma lista completa de caminhos de contador, remova o pipeline ( `|` ) e o `Where-Object` comando.

O `$_` é uma variável automática para o objeto atual no pipeline.
Para obter mais informações, consulte [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).

```powershell
(Get-Counter -ListSet Memory).Paths | Where-Object { $_ -like "*Cache*" }
```

```Output
\Memory\Cache Faults/sec
\Memory\Cache Bytes
\Memory\Cache Bytes Peak
\Memory\System Cache Resident Bytes
\Memory\Standby Cache Reserve Bytes
\Memory\Standby Cache Normal Priority Bytes
\Memory\Standby Cache Core Bytes
\Memory\Long-Term Average Standby Cache Lifetime (s)
```

`Get-Counter` usa o parâmetro **ListSet** para especificar o conjunto de contadores de **memória** . O comando é colocado entre parênteses para que a propriedade **Paths** retorne cada caminho como uma cadeia de caracteres. Os objetos são enviados ao pipeline para `Where-Object` . `Where-Object` usa a variável `$_` para processar cada objeto e usa o `-like` operador para localizar correspondências para a cadeia de caracteres `*Cache*` . Os asteriscos ( `*` ) são curingas para quaisquer caracteres.

### Exemplo 9: usar a propriedade PathsWithInstances para obter nomes de caminho formatados

Este exemplo obtém os nomes de caminho formatados que incluem as instâncias para os contadores de desempenho do **disco físico** .

```powershell
(Get-Counter -ListSet PhysicalDisk).PathsWithInstances
```

```Output
\PhysicalDisk(0 C:)\Current Disk Queue Length
\PhysicalDisk(_Total)\Current Disk Queue Length
\PhysicalDisk(0 C:)\% Disk Time
\PhysicalDisk(_Total)\% Disk Time
\PhysicalDisk(0 C:)\Avg. Disk Queue Length
\PhysicalDisk(_Total)\Avg. Disk Queue Length
\PhysicalDisk(0 C:)\% Disk Read Time
\PhysicalDisk(_Total)\% Disk Read Time
```

`Get-Counter` usa o parâmetro **ListSet** para especificar o conjunto de contadores de **PhysicalDisk** . O comando é colocado entre parênteses para que a propriedade **PathsWithInstances** retorne cada instância de caminho como uma cadeia de caracteres.

### Exemplo 10: obter um único valor para cada contador em um conjunto de contadores

Neste exemplo, um único valor é retornado para cada contador de desempenho no conjunto de contadores de **memória** do computador local.

```powershell
$MemCounters = (Get-Counter -ListSet Memory).Paths
Get-Counter -Counter $MemCounters
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/19/2019 12:05:00        \\Computer01\memory\page faults/sec :
                          868.772077545597

                          \\Computer01\memory\available bytes :
                          9031176192

                          \\Computer01\memory\committed bytes :
                          8242982912

                          \\Computer01\memory\commit limit :
                          19603333120
```

`Get-Counter` usa o parâmetro **ListSet** para especificar o conjunto de contadores de **memória** . O comando é colocado entre parênteses para que a propriedade **Paths** retorne cada caminho como uma cadeia de caracteres. Os caminhos são armazenados na `$MemCounters` variável. `Get-Counter` usa o parâmetro **Counter** para especificar os caminhos do contador na `$MemCounters` variável.

### Exemplo 11: exibir os valores de propriedade de um objeto

Os valores de propriedade no objeto **PerformanceCounterSample** representam cada amostra de dados. Neste exemplo, usamos as propriedades do objeto de **Contraamostrações** para examinar, selecionar, classificar e agrupar os dados.

```powershell
$Counter = "\\Server01\Process(Idle)\% Processor Time"
$Data = Get-Counter $Counter
$Data.CounterSamples | Format-List -Property *
```

```Output
Path             : \\Server01\process(idle)\% processor time
InstanceName     : idle
CookedValue      : 198.467899571389
RawValue         : 14329160321003
SecondValue      : 128606459528326201
MultipleCount    : 1
CounterType      : Timer100Ns
Timestamp        : 6/19/2019 12:20:49
Timestamp100NSec : 128606207528320000
Status           : 0
DefaultScale     : 0
TimeBase         : 10000000
```

O caminho do contador é armazenado na `$Counter` variável. `Get-Counter` Obtém uma amostra dos valores do contador e armazena os resultados na `$Data` variável. A `$Data` variável usa a propriedade de **contraamostrações** para obter as propriedades do objeto. O objeto é enviado ao pipeline para `Format-List` . O parâmetro **Property** usa um curinga asterisco ( `*` ) para selecionar todas as propriedades.

### Exemplo 12: valores de matriz do contador de desempenho

Neste exemplo, uma variável armazena cada contador de desempenho. A propriedade de **Metaamostras** é uma matriz que pode exibir valores de contador específicos.

Para exibir cada exemplo de contador, use `$Counter.CounterSamples` .

```powershell
$Counter = Get-Counter -Counter "\Processor(*)\% Processor Time"
$Counter.CounterSamples[0]
```

```Output
Path                                         InstanceName        CookedValue
----                                         ------------        -----------
\\Computer01\processor(0)\% processor time   0              1.33997091699662
```

`Get-Counter` usa o parâmetro **Counter** para especificar o contador `\Processor(*)\% Processor Time` . Os valores são armazenados na `$Counter` variável.
`$Counter.CounterSamples[0]` exibe o valor da matriz para o primeiro valor do contador.

### Exemplo 13: comparar valores de contadores de desempenho

Este exemplo localiza a quantidade de tempo do processador usada por cada processador no computador local. A propriedade **Comsamples** é usada para comparar os dados do contador com um valor especificado.

Para exibir cada exemplo de contador, use `$Counter.CounterSamples` .

```powershell
$Counter = Get-Counter -Counter "\Processor(*)\% Processor Time"
$Counter.CounterSamples | Where-Object { $_.CookedValue -lt "20" }
```

```Output
Path                                         InstanceName        CookedValue
----                                         ------------        -----------
\\Computer01\processor(0)\% processor time   0              12.6398025240208
\\Computer01\processor(1)\% processor time   1              15.7598095767344
```

`Get-Counter` usa o parâmetro **Counter** para especificar o contador `\Processor(*)\% Processor Time` . Os valores são armazenados na `$Counter` variável. Os objetos armazenados no `$Counter.CounterSamples` são enviados pelo pipeline. `Where-Object` usa um bloco de script para comparar cada valor de objeto com um valor especificado de 20. O `$_.CookedValue` é uma variável para o objeto atual no pipeline. Os contadores com um **CookedValue** que é inferior a 20 são exibidos.

### Exemplo 14: classificar dados do contador de desempenho

Este exemplo mostra como classificar dados do contador de desempenho. O exemplo localiza os processos no computador que estão usando a maior parte do tempo do processador durante o exemplo.

```powershell
$Procs = Get-Counter -Counter "\Process(*)\% Processor Time"
$Procs.CounterSamples | Sort-Object -Property CookedValue -Descending |
   Format-Table -Property Path, InstanceName, CookedValue -AutoSize
```

```Output
Path                                                         InstanceName             CookedValue
----                                                         ------------             -----------
\\Computer01\process(_total)\% processor time                _total              395.464129650573
\\Computer01\process(idle)\% processor time                  idle                389.356575524695
\\Computer01\process(mssense)\% processor time               mssense             3.05377706293879
\\Computer01\process(csrss#1)\% processor time               csrss               1.52688853146939
\\Computer01\process(microsoftedgecp#10)\% processor time    microsoftedgecp     1.52688853146939
\\Computer01\process(runtimebroker#5)\% processor time       runtimebroker                      0
\\Computer01\process(settingsynchost)\% processor time       settingsynchost                    0
\\Computer01\process(microsoftedgecp#16)\% processor time    microsoftedgecp                    0
```

`Get-Counter` usa o parâmetro **Counter** para especificar o `\Process(*)\% Processor Time` contador para todos os processos no computador local. O resultado é armazenado na `$Procs` variável. A `$Procs` variável com a propriedade **comsamples** envia os objetos **PerformanceCounterSample** para baixo do pipeline. `Sort-Object` usa o parâmetro **Property** para classificar os objetos por **CookedValue** em ordem **decrescente** . `Format-Table` usa o parâmetro **Property** para selecionar as colunas para a saída. O parâmetro **AutoSize** ajusta as larguras das colunas para minimizar o truncamento.

## PARAMETERS

### -ComputerName

Especifica um nome de computador ou uma matriz separada por vírgulas de nomes de computadores **remotos** . Use o nome NetBIOS, um endereço IP ou o nome de domínio totalmente qualificado do computador.

Para obter dados do contador de desempenho do computador **local** , exclua o parâmetro **ComputerName** .
Para saída como um **ListSet** que contém a coluna **MachineName** , um ponto ( `.` ) indica o computador local.

`Get-Counter` Não depende da comunicação remota do PowerShell. Você pode usar o parâmetro **ComputerName** mesmo que o computador não esteja configurado para executar comandos remotos.

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

### -Continuous

Quando o **contínuo** for especificado, `Get-Counter` Obtém amostras até que você pressione <kbd>Ctrl</kbd> + <kbd>C</kbd>. Os exemplos são obtidos a cada segundo para cada contador de desempenho especificado. Use o parâmetro **SampleInterval** para aumentar o intervalo entre amostras contínuas.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Contador

Especifica o caminho para um ou mais caminhos de contador. Os caminhos são inseridos como uma matriz separada por vírgula, uma variável ou valores de um arquivo de texto. Você pode enviar cadeias de caracteres de caminho do contador para baixo no pipeline para `Get-Counter` .

Os caminhos de contador usam a seguinte sintaxe:

`\\ComputerName\CounterSet(Instance)\CounterName`

`\CounterSet(Instance)\CounterName`

Por exemplo:

`\\Server01\Processor(*)\% User Time`

`\Processor(*)\% User Time`

O `\\ComputerName` é opcional em um caminho de contador de desempenho. Se o caminho do contador não incluir o nome do computador, o `Get-Counter` usará o computador local.

Um asterisco ( `*` ) na instância é um caractere curinga para obter todas as instâncias do contador.

```yaml
Type: System.String[]
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -ListSet

Lista os conjuntos de contadores de desempenho nos computadores. Use um asterisco ( `*` ) para especificar todos os conjuntos de contadores. Insira um nome ou uma cadeia de caracteres separada por vírgulas de nomes de conjuntos de contadores. Você pode enviar nomes de conjuntos de contadores para baixo do pipeline.

Para obter um contador, defina os caminhos de contador formatados, use o parâmetro **ListSet** . Os **caminhos** e as propriedades **PathsWithInstances** de cada conjunto de contadores contêm os caminhos de contador individuais formatados como uma cadeia de caracteres.

Você pode salvar as cadeias de caminho do contador em uma variável ou usar o pipeline para enviar a cadeia de caracteres para outro `Get-Counter` comando.

Por exemplo, para enviar cada caminho do contador de **processador** para `Get-Counter` :

`Get-Counter -ListSet Processor | Get-Counter`

> [!NOTE]
> No PowerShell 7, `Get-Counter` o não pode recuperar a propriedade **Description** do conjunto de contadores. A **Descrição** é definida como `$null` .

```yaml
Type: System.String[]
Parameter Sets: ListSetSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### -MaxSamples

Especifica o número de amostras para obter de cada contador de desempenho especificado. Para obter um fluxo constante de exemplos, use o parâmetro **Continuous** .

Se o parâmetro **MaxSamples** não for especificado, apenas obterá `Get-Counter` um exemplo para cada contador especificado.

Para coletar um grande conjunto de dados, execute `Get-Counter` como um trabalho em segundo plano do PowerShell. Para obter mais informações, consulte [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md).

```yaml
Type: System.Int64
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SampleInterval

Especifica o número de segundos entre as amostras para cada contador de desempenho especificado. Se o parâmetro **SampleInterval** não for especificado, o `Get-Counter` usará um intervalo de um segundo.

```yaml
Type: System.Int32
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String[]

`Get-Counter` aceita a entrada de pipeline para caminhos de contador e nomes de conjuntos de contadores.

## SAÍDAS

### Microsoft. PowerShell. Commands. getcontador. CounterSet, Microsoft. PowerShell. Commands. getcounterer. PerformanceCounterSampleSet, Microsoft. PowerShell. Commands. GetCounter. PerformanceCounterSample

Para exibir as propriedades de um objeto, envie a saída para baixo do pipeline para `Get-Member` . Os tipos de objeto que são saída são os seguintes:

Parâmetro **ListSet** : **Microsoft. PowerShell. Commands. GetCounter**

Parâmetro do **contador** : **Microsoft. PowerShell. Commands. GetCounter. PerformanceCounterSampleSet**

Propriedade de **Contraamostrações** : **Microsoft. PowerShell. Commands. getcounterer. PerformanceCounterSample**

## OBSERVAÇÕES

Se nenhum parâmetro for especificado, `Get-Counter` Obtém um exemplo para cada contador de desempenho especificado. Use os parâmetros **MaxSamples** e **Continuous** para obter mais exemplos.

`Get-Counter` usa um intervalo de um segundo entre exemplos. Use o parâmetro **SampleInterval** para aumentar o intervalo.

Os valores **MaxSamples** e **SampleInterval** se aplicam a todos os contadores em cada computador no comando. Para definir valores diferentes para contadores diferentes, insira `Get-Counter` comandos separados.

No PowerShell 7, ao usar o parâmetro **ListSet** , `Get-Counter` o não pode recuperar a propriedade **Description** do conjunto de contadores. A **Descrição** é definida como `$null` .

## LINKS RELACIONADOS

[about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md)

[Format-List](../Microsoft.PowerShell.Utility/Format-List.md)

[Format-Table](../Microsoft.PowerShell.Utility/Format-Table.md)

[Get-Member](../Microsoft.PowerShell.Utility/Get-Member.md)

[Receive-Job](../Microsoft.PowerShell.Core/Receive-Job.md)

[Start-Job](../Microsoft.PowerShell.Core/Start-Job.md)

[Where-Object](..//Microsoft.PowerShell.Core/Where-Object.md)

