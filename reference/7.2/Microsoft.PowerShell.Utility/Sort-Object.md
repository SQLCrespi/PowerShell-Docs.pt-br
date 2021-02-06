---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/sort-object?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Sort-Object
ms.openlocfilehash: fead3b3d109a79186bc82f3c9f212f11f7b0bc57
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596796"
---
# Sort-Object

## SINOPSE
Classifica os objetos por valores de propriedade.

## SYNTAX

### Padrão (padrão)

```
Sort-Object [-Stable] [-Descending] [-Unique] [-InputObject <PSObject>] [[-Property] <Object[]>]
 [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

### Superior

```
Sort-Object [-Descending] [-Unique] -Top <Int32> [-InputObject <PSObject>] [[-Property] <Object[]>]
 [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

### Inferior

```
Sort-Object [-Descending] [-Unique] -Bottom <Int32> [-InputObject <PSObject>] [[-Property] <Object[]>]
 [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

## DESCRIPTION

O `Sort-Object` cmdlet classifica os objetos em ordem crescente ou decrescente com base em valores de propriedade de objeto. Se as propriedades de classificação não forem incluídas em um comando, o PowerShell usará as propriedades de classificação padrão do primeiro objeto de entrada. Se o tipo do objeto de entrada não tiver nenhuma propriedade de classificação padrão, o PowerShell tentará comparar os próprios objetos. Para obter mais informações, consulte a seção [observações](#notes) .

Você pode classificar objetos por uma única propriedade ou várias propriedades. Várias propriedades usam tabelas de hash para classificar em ordem crescente, ordem decrescente ou uma combinação de ordens de classificação. As propriedades são classificadas como diferencia maiúsculas de minúsculas ou não diferencia maiúsculas de minúsculas. Use o parâmetro **exclusivo** para eliminar duplicatas da saída.

## EXEMPLOS

### Exemplo 1: classificar o diretório atual por nome

Este exemplo classifica os arquivos e subdiretórios em um diretório.

```
PS> Get-ChildItem -Path C:\Test | Sort-Object

    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/13/2019     08:55             26 anotherfile.txt
-a----        2/13/2019     13:26             20 Bfile.txt
-a----        2/12/2019     15:40         118014 Command.txt
-a----         2/1/2019     08:43            183 CreateTestFile.ps1
d-----        2/25/2019     18:25                Files
d-----        2/25/2019     18:24                Logs
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
-a----        2/12/2019     16:24             23 Zsystemlog.log
```

O `Get-ChildItem` cmdlet obtém os arquivos e subdiretórios do diretório especificado pelo parâmetro **Path** , **C:\test**. Os objetos são enviados para o pipeline para o `Sort-Object` cmdlet.
`Sort-Object` não especifica uma propriedade para que a saída seja classificada pela propriedade de classificação padrão, **Name**.

### Exemplo 2: classificar o diretório atual por comprimento do arquivo

Esse comando exibe os arquivos no diretório atual por comprimento em ordem crescente.

```
PS> Get-ChildItem -Path C:\Test -File | Sort-Object -Property Length

    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/13/2019     13:26             20 Bfile.txt
-a----        2/12/2019     16:24             23 Zsystemlog.log
-a----        2/13/2019     08:55             26 anotherfile.txt
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
-a----         2/1/2019     08:43            183 CreateTestFile.ps1
-a----        2/12/2019     15:40         118014 Command.txt
```

O `Get-ChildItem` cmdlet obtém os arquivos do diretório especificado pelo parâmetro **Path** .
O parâmetro **File** especifica que `Get-ChildItem` somente Obtém os objetos de arquivo. Os objetos são enviados para o pipeline para o `Sort-Object` cmdlet. `Sort-Object` usa o parâmetro **Length** para classificar os arquivos por comprimento em ordem crescente.

### Exemplo 3: classificar processos por uso de memória

Este exemplo exibe processos com o maior uso de memória com base em seu tamanho de conjunto de trabalho (WS).

```
PS> Get-Process | Sort-Object -Property WS | Select-Object -Last 5

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    136   193.92     217.11     889.16   87492   8 OUTLOOK
    112   347.73     297.02      95.19  106908   8 Teams
    206   266.54     323.71      37.17   60620   8 MicrosoftEdgeCP
     35   552.19     549.94     131.66    6552   8 Code
      0     1.43     595.12       0.00    2780   0 Memory Compression
```

O `Get-Process` cmdlet obtém a lista de processos em execução no computador. Os objetos de processo são enviados por meio do pipeline para o `Sort-Object` cmdlet. `Sort-Object` usa o parâmetro **Property** para classificar os objetos por **WS**. Os objetos são enviados para o pipeline para o `Select-Object` cmdlet.
`Select-Object` usa o **último** parâmetro para especificar os últimos cinco objetos, que são os objetos com o maior uso do **WS** .

No PowerShell 6, a `Sort-Object` **parte inferior** do parâmetro é uma alternativa para `Select-Object` . Por exemplo, `Get-Process | Sort-Object -Property WS -Bottom 5`.

### Exemplo 4: classificar objetos HistoryInfo por ID

Esse comando classifica os objetos **HistoryInfo** da sessão do PowerShell usando a propriedade **ID** . Cada sessão do PowerShell tem seu próprio histórico de comandos.

```
PS> Get-History | Sort-Object -Property Id -Descending

  Id CommandLine
  -- -----------
  10 Get-Command Sort-Object -Syntax
   9 $PSVersionTable
   8 Get-Command Sort-Object -Syntax
   7 Get-Command Sort-Object -ShowCommandInfo
   6 Get-ChildItem -Path C:\Test | Sort-Object -Property Length
   5 Get-Help Clear-History -online
   4 Get-Help Clear-History -full
   3 Get-ChildItem | Get-Member
   2 Get-Command Sort-Object -Syntax
   1 Set-Location C:\Test\
```

O `Get-History` cmdlet obtém os objetos de histórico da sessão atual do PowerShell. Os objetos são enviados para o pipeline para o `Sort-Object` cmdlet. `Sort-Object` usa o parâmetro **Property** para classificar os objetos por **ID**. O parâmetro **decrescente** classifica o histórico de comandos do mais recente para o mais antigo.

### Exemplo 5: usar uma tabela de hash para classificar Propriedades em ordem crescente e decrescente

Este exemplo usa duas propriedades para classificar os objetos, **status** e **DisplayName**. O **status** é classificado em ordem decrescente e **DisplayName** é classificado em ordem crescente.

Uma tabela de hash é usada para especificar o valor do parâmetro de **Propriedade** . A tabela de hash usa uma expressão para especificar os nomes de propriedade e as ordens de classificação. Para obter informações sobre tabelas de hash, confira [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).

A propriedade de **status** usada na tabela de hash é uma propriedade enumerada.
Para obter mais informações, consulte [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).

```
PS C:\> Get-Service | Sort-Object -Property @{Expression = "Status"; Descending = $True}, @{Expression = "DisplayName"; Descending = $False}

Status   Name               DisplayName
------   ----               -----------
Running  Appinfo            Application Information
Running  BthAvctpSvc        AVCTP service
Running  BrokerInfrastru... Background Tasks Infrastructure Ser...
Running  BDESVC             BitLocker Drive Encryption Service
Running  CoreMessagingRe... CoreMessaging
Running  VaultSvc           Credential Manager
Running  DsSvc              Data Sharing Service
Running  Dhcp               DHCP Client
...
Stopped  ALG                Application Layer Gateway Service
Stopped  AppMgmt            Application Management
Stopped  BITS               Background Intelligent Transfer Ser...
Stopped  wbengine           Block Level Backup Engine Service
Stopped  BluetoothUserSe... Bluetooth User Support Service_14fb...
Stopped  COMSysApp          COM+ System Application
Stopped  smstsmgr           ConfigMgr Task Sequence Agent
Stopped  DeviceInstall      Device Install Service
Stopped  MSDTC              Distributed Transaction Coordinator
```

O `Get-Service` cmdlet obtém a lista de serviços no computador. Os objetos de serviço são enviados pelo pipeline para o `Sort-Object` cmdlet. `Sort-Object` usa o parâmetro **Property** com uma tabela de hash para especificar os nomes de propriedade e as ordens de classificação. O parâmetro **Property** é classificado por duas propriedades, **status** em ordem decrescente e **DisplayName** em ordem crescente.

O **status** é uma propriedade enumerada. **Stopped** tem um valor de **1** e **em execução** tem um valor de **4**. O parâmetro **decrescente** é definido como para `$True` que os processos **em execução** sejam exibidos antes dos processos **interrompidos** . **DisplayName** define o parâmetro **decrescente** como `$False` para classificar os nomes de exibição em ordem alfabética.

### Exemplo 6: classificar arquivos de texto por período de tempo

Esse comando classifica os arquivos de texto em ordem decrescente pelo período de tempo entre **CreationTime** e **LastWriteTime**.

```
PS> Get-ChildItem -Path C:\Test\*.txt | Sort-Object -Property @{Expression = {$_.CreationTime - $_.LastWriteTime}; Descending = $False} | Format-Table CreationTime, LastWriteTime, FullName

CreationTime          LastWriteTime        FullName
------------          -------------        --------
11/21/2018 12:39:01   2/26/2019 08:59:36   C:\Test\test2.txt
12/4/2018 08:29:41    2/26/2019 08:57:05   C:\Test\powershell_list.txt
2/20/2019 08:15:59    2/26/2019 12:09:43   C:\Test\CreateTestFile.txt
2/20/2019 08:15:59    2/26/2019 12:07:41   C:\Test\Command.txt
2/20/2019 08:15:59    2/26/2019 08:57:52   C:\Test\ReadOnlyFile.txt
11/29/2018 15:16:50   12/4/2018 16:16:24   C:\Test\LogData.txt
2/25/2019 18:25:11    2/26/2019 12:08:47   C:\Test\Zsystemlog.txt
2/25/2019 18:25:11    2/26/2019 08:55:33   C:\Test\Bfile.txt
2/26/2019 08:46:59    2/26/2019 12:12:19   C:\Test\LogFile3.txt
```

O `Get-ChildItem` cmdlet usa o parâmetro **Path** para especificar o diretório **C:\test** e todos os `*.txt` arquivos. Os objetos são enviados para o pipeline para o `Sort-Object` cmdlet.
`Sort-Object` usa o parâmetro **Property** com uma tabela de hash para determinar cada intervalo de tempo dos arquivos entre **CreationTime** e **LastWriteTime**. O parâmetro **decrescente** é definido como `$False` para classificar na ordem de mais longo do que o intervalo de tempo mais curto.

### Exemplo 7: classificar nomes em um arquivo de texto

Este exemplo mostra como classificar uma lista de um arquivo de texto. O arquivo original é exibido como uma lista não classificada. `Sort-Object` classifica o conteúdo e, em seguida, classifica o conteúdo com o parâmetro **exclusivo** que remove duplicatas.

```
PS> Get-Content -Path C:\Test\ServerNames.txt
localhost
server01
server25
LOCALHOST
Server19
server3
localhost

PS> Get-Content -Path C:\Test\ServerNames.txt | Sort-Object
localhost
LOCALHOST
localhost
server01
Server19
server25
server3

PS> Get-Content -Path C:\Test\ServerNames.txt | Sort-Object -Unique
localhost
server01
Server19
server25
server3
```

O `Get-Content` cmdlet usa o parâmetro **Path** para especificar o diretório e o nome do arquivo. O arquivo **ServerNames.txt** contém uma lista não classificada de nomes de computador.

O `Get-Content` cmdlet usa o parâmetro **Path** para especificar o diretório e o nome do arquivo. O arquivo **ServerNames.txt** contém uma lista não classificada de nomes de computador. Os objetos são enviados para o pipeline para o `Sort-Object` cmdlet. `Sort-Object` classifica a lista na ordem padrão, crescente.

O `Get-Content` cmdlet usa o parâmetro **Path** para especificar o diretório e o nome do arquivo. O arquivo **ServerNames.txt** contém uma lista não classificada de nomes de computador. Os objetos são enviados para o pipeline para o `Sort-Object` cmdlet. `Sort-Object` usa o parâmetro **exclusivo** para remover nomes de computadores duplicados. A lista é classificada na ordem padrão, crescente.

### Exemplo 8: classificar uma cadeia de caracteres como um número inteiro

Este exemplo mostra como classificar um arquivo de texto que contém objetos de cadeia de caracteres como inteiros. Você pode enviar cada comando para baixo do pipeline para `Get-Member` e verificar se os objetos são cadeias de caracteres em vez de inteiros. Para esses exemplos, o `ProductId.txt` arquivo contém uma lista não classificada de números de produtos.

No primeiro exemplo, `Get-Content` Obtém o conteúdo do arquivo e as linhas de pipes para o `Sort-Object` cmdlet. `Sort-Object` classifica os objetos de cadeia de caracteres em ordem crescente.

```
PS> Get-Content -Path C:\Test\ProductId.txt | Sort-Object
0
1
12345
1500
2
2800
3500
4100
500
6200
77
88
99999

PS> Get-Content -Path C:\Test\ProductId.txt | Sort-Object {[int]$_}
0
1
2
77
88
500
1500
2800
3500
4100
6200
12345
99999
```

No segundo exemplo, `Get-Content` Obtém o conteúdo do arquivo e as linhas de pipes para o `Sort-Object` cmdlet. `Sort-Object` usa um bloco de script para converter as cadeias de caracteres em números inteiros. No código de exemplo, `[int]` converte a cadeia de caracteres em um número inteiro e `$_` representa cada cadeia de caracteres à medida que ela é exibida no pipeline. Os objetos Integer são enviados ao pipeline para o `Sort-Object` cmdlet.
`Sort-Object` classifica os objetos de inteiro em ordem numérica.

### Exemplo 9: usando classificações estáveis

Quando você usa os parâmetros **superior**, **inferior** ou **estável** , os objetos classificados são entregues na ordem em que foram recebidos `Sort-Object` quando os critérios de classificação são iguais. Neste exemplo, estamos classificando os números um a 20 pelo valor ' módulo 3 '. O valor do módulo varia de zero a dois.

```powershell
PS> 1..20 |Sort-Object {$_ % 3}
18
3
15
6
12
9
1
16
13
10
7
4
19
11
8
14
5
17
2
20

PS> 1..20 |Sort-Object {$_ % 3} -Stable
3
6
9
12
15
18
1
4
7
10
13
16
19
2
5
8
11
14
17
20
```

A saída da primeira classificação é agrupada corretamente pelo valor de módulo, mas os itens individuais não são classificados dentro do intervalo de módulos. A segunda classificação usa a opção **estável** para retornar uma classificação estável.

## PARAMETERS

### -Inferior

Especifica o número de objetos a serem obtidos do final de uma matriz de objetos classificados. Isso resulta em uma classificação estável.

Esse parâmetro foi introduzido no PowerShell 6,0.

```yaml
Type: System.Int32
Parameter Sets: Bottom
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CaseSensitive

Indica que a classificação diferencia maiúsculas de minúsculas. Por padrão, as classificações não diferenciam maiúsculas de minúsculas.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Case-insensitive
Accept pipeline input: False
Accept wildcard characters: False
```

### -Culture

Especifica a configuração cultural a ser usada para classificações. Use `Get-Culture` para exibir a configuração de cultura do sistema.

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

### -Decrescente

Indica que `Sort-Object` o classifica os objetos em ordem decrescente. O padrão é a ordem crescente.

Para classificar várias propriedades com diferentes ordens de classificação, use uma tabela de hash. Por exemplo, com uma tabela de hash, você pode classificar uma propriedade em ordem crescente e outra propriedade em ordem decrescente.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Ascending
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Para classificar objetos, envie-os para o pipeline para `Sort-Object` . Se você usar o parâmetro **InputObject** para enviar uma coleção de itens, o `Sort-Object` receberá um objeto que representa a coleção. Como um objeto não pode ser classificado, `Sort-Object` o retorna a coleção inteira inalterada.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Propriedade

Especifica os nomes de propriedade que `Sort-Object` o usa para classificar os objetos. Caracteres curinga são permitidos.
Os objetos são classificados com base nos valores de propriedade. Se você não especificar uma propriedade, `Sort-Object` o classificará com base nas propriedades padrão do tipo de objeto ou dos próprios objetos.

Várias propriedades podem ser classificadas em ordem crescente, ordem decrescente ou uma combinação de ordens de classificação. Quando você especifica várias propriedades, os objetos são classificados pela primeira propriedade. Se vários objetos tiverem o mesmo valor para a primeira propriedade, esses objetos serão classificados pela segunda propriedade. Esse processo continua até que não hajam mais propriedades especificadas ou grupos de objetos.

O valor do parâmetro de **Propriedade** pode ser uma propriedade calculada. Para criar uma propriedade calculada, use uma tabela de hash.

As chaves válidas para uma tabela de hash são as seguintes:

- `expression` - `<string>` ou `<script block>`
- `ascending` or `descending` - `<boolean>`

Para obter mais informações, consulte [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: Default properties
Accept pipeline input: False
Accept wildcard characters: True
```

### -Superior

Especifica o número de objetos a serem obtidos do início de uma matriz de objetos classificados. Isso resulta em uma classificação estável.

Esse parâmetro foi introduzido no PowerShell 6,0.

```yaml
Type: System.Int32
Parameter Sets: Top
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Exclusivo

Indica que o `Sort-Object` elimina duplicatas e retorna somente os membros exclusivos da coleção. A primeira instância de um valor exclusivo é incluída na saída classificada.

**Exclusivo** não diferencia maiúsculas de minúsculas. Cadeias de caracteres que diferem apenas por maiúsculas e minúsculas são consideradas iguais.
Por exemplo, caractere e caractere.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: All
Accept pipeline input: False
Accept wildcard characters: False
```

### -Estável

Os objetos classificados são entregues na ordem em que foram recebidos quando os critérios de classificação são iguais.

Esse parâmetro foi adicionado no PowerShell v 6.2.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default
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

### System. Management. Automation. PSObject

Você pode canalizar os objetos a serem classificados `Sort-Object` .

## SAÍDAS

### System. Management. Automation. PSObject

`Sort-Object` Retorna os objetos classificados.

## OBSERVAÇÕES

O `Sort-Object` cmdlet classifica objetos com base nas propriedades especificadas no comando ou nas propriedades de classificação padrão para o tipo de objeto. As propriedades de classificação padrão são definidas usando o `PropertySet` nome `DefaultKeyPropertySet` em um `types.ps1xml` arquivo. Para obter mais informações, consulte [about_Types.ps1XML](/powershell/module/Microsoft.PowerShell.Core/About/about_Types.ps1xml).

Se um objeto não tiver uma das propriedades especificadas, o valor da propriedade desse objeto será interpretado `Sort-Object` como **nulo** e colocado no final da ordem de classificação.

Quando nenhuma propriedade de classificação estiver disponível, o PowerShell tentará comparar os próprios objetos.
`Sort-Object` usa o método **Compare** para cada propriedade. Se uma propriedade não implementar **IComparable**, o cmdlet converterá o valor da propriedade em uma cadeia de caracteres e usará o método **Compare** para **System. String**. Para obter mais informações, consulte o [método PSObject. CompareTo (Object)](/dotnet/api/system.management.automation.psobject.compareto).

Se você classificar em uma propriedade enumerada, como **status**, `Sort-Object` classifica os valores de enumeração. Para serviços do Windows, **parado** tem um valor de **1** e **em execução** tem um valor de **4**.
**Parado** é classificado antes da **execução** devido aos valores enumerados. Para obter mais informações, consulte [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).

O desempenho do algoritmo de classificação é mais lento ao fazer uma classificação estável.

## LINKS RELACIONADOS

[about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)

[Compare-Object](Compare-Object.md)

[ForEach-Object](../Microsoft.PowerShell.Core/ForEach-Object.md)

[Group-Object](Group-Object.md)

[Measure-Object](Measure-Object.md)

[New-Object](New-Object.md)

[Select-Object](Select-Object.md)

[Tee-Object](Tee-Object.md)
