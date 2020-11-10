---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-process?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Process
ms.openlocfilehash: 360b1f045899dec20a30be022e043947f47b52b7
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94391129"
---
# Get-Process

## SINOPSE
Obtém os processos em execução no computador local.

## SYNTAX

### Nome (padrão)

```
Get-Process [[-Name] <String[]>] [-Module] [-FileVersionInfo] [<CommonParameters>]
```

### NameWithUserName

```
Get-Process [[-Name] <String[]>] -IncludeUserName [<CommonParameters>]
```

### ID

```
Get-Process -Id <Int32[]> [-Module] [-FileVersionInfo] [<CommonParameters>]
```

### IdWithUserName

```
Get-Process -Id <Int32[]> -IncludeUserName [<CommonParameters>]
```

### InputObject

```
Get-Process -InputObject <Process[]> [-Module] [-FileVersionInfo] [<CommonParameters>]
```

### InputObjectWithUserName

```
Get-Process -InputObject <Process[]> -IncludeUserName [<CommonParameters>]
```

## DESCRIPTION

O `Get-Process` cmdlet obtém os processos em um computador local ou remoto.

Sem parâmetros, esse cmdlet obtém todos os processos no computador local. Você também pode especificar um processo específico por nome do processo ou ID do processo (PID) ou passar um objeto de processo por meio do pipeline para esse cmdlet.

Por padrão, esse cmdlet retorna um objeto de processo que tem informações detalhadas sobre o processo e dá suporte a métodos que permitem iniciar e parar o processo. Você também pode usar os parâmetros do `Get-Process` cmdlet para obter informações de versão de arquivo para o programa que é executado no processo e para obter os módulos carregados pelo processo.

## EXEMPLOS

### Exemplo 1: obter uma lista de todos os processos ativos no computador local

```powershell
Get-Process
```

Esse comando obtém uma lista de todos os processos ativos em execução no computador local. Para obter uma definição de cada coluna, consulte a seção [observações](#notes) .

### Exemplo 2: obter todos os dados disponíveis sobre um ou mais processos

```powershell
Get-Process winword, explorer | Format-List *
```

Esse comando obtém todos os dados disponíveis sobre os processos Winword e Explorer no computador. Ele usa o parâmetro **Name** para especificar os processos, mas omite o nome de parâmetro opcional. O operador de pipeline `|` passa os dados para o `Format-List` cmdlet, que exibe todas as propriedades disponíveis `*` dos objetos de processo do Winword e do Explorer.

Você também pode identificar os processos pelas suas IDs. Por exemplo, `Get-Process -Id 664, 2060` .

### Exemplo 3: obter todos os processos com um conjunto de trabalho maior que um tamanho especificado

```powershell
Get-Process | Where-Object {$_.WorkingSet -gt 20000000}
```

Esse comando obtém todos os processos que têm um conjunto de trabalho de mais de 20 MB. Ele usa o `Get-Process` cmdlet para obter todos os processos em execução. O operador de pipeline `|` passa os objetos de processo para o `Where-Object` cmdlet, que seleciona apenas o objeto com um valor maior que 20 milhões bytes para a propriedade **WorkingSet** .

O **WorkingSet** é uma das muitas propriedades de objetos de processo. Para ver todas as propriedades, digite `Get-Process | Get-Member` . Por padrão, os valores de todas as propriedades de quantidade são em bytes, ainda que a exibição padrão as liste em quilobytes e megabytes.

### Exemplo 4: listar processos no computador em grupos com base na prioridade

```powershell
$A = Get-Process
$A | Get-Process | Format-Table -View priority
```

Esses comandos listam os processos no computador em grupos com base em sua classe de prioridade. O primeiro comando obtém todos os processos no computador e os armazena na `$A` variável.

O segundo comando canaliza o objeto de **processo** armazenado na `$A` variável para o `Get-Process` cmdlet e, em seguida, para o `Format-Table` cmdlet, que formata os processos usando a exibição de **prioridade** .

A exibição de **prioridade** e outras exibições são definidas nos arquivos de formato ps1xml no diretório base do PowerShell ( `$pshome` ).

### Exemplo 5: adicionar uma propriedade à exibição de saída de Get-Process padrão

```powershell
Get-Process pwsh | Format-Table `
    @{Label = "NPM(K)"; Expression = {[int]($_.NPM / 1024)}},
    @{Label = "PM(K)"; Expression = {[int]($_.PM / 1024)}},
    @{Label = "WS(K)"; Expression = {[int]($_.WS / 1024)}},
    @{Label = "VM(M)"; Expression = {[int]($_.VM / 1MB)}},
    @{Label = "CPU(s)"; Expression = {if ($_.CPU) {$_.CPU.ToString("N")}}},
    Id, MachineName, ProcessName -AutoSize
```

```Output
NPM(K) PM(K) WS(K) VM(M) CPU(s)   Id MachineName ProcessName
------ ----- ----- ----- ------   -- ----------- -----------
     6 23500 31340   142 1.70   1980 .           pwsh
     6 23500 31348   142 2.75   4016 .           pwsh
    27 54572 54520   576 5.52   4428 .           pwsh
```

Este exemplo recupera processos do computador local e de um computador remoto (S1). Os processos recuperados são canalizados para o `Format-Table` comando que adiciona a propriedade **MachineName** à exibição de `Get-Process` saída padrão.

### Exemplo 6: obter informações de versão para um processo

```powershell
Get-Process pwsh -FileVersionInfo
```

```Output
ProductVersion   FileVersion      FileName
--------------   -----------      --------
6.1.2            6.1.2            C:\Program Files\PowerShell\6\pwsh.exe
```

Esse comando usa o parâmetro **FileVersionInfo** para obter as informações de versão para o arquivo de pwsh.exe que é o módulo principal para o processo do PowerShell.

Para executar esse comando com processos que não são de sua propriedade no Windows Vista e em versões posteriores do Windows, você deve abrir o PowerShell com a opção Executar como administrador.

### Exemplo 7: obter módulos carregados com o processo especificado

```powershell
Get-Process SQL* -Module
```

Esse comando usa o parâmetro **Module** para obter os módulos que foram carregados pelo processo.
Esse comando obtém os módulos para os processos que têm nomes que começam com SQL.

Para executar esse comando no Windows Vista e em versões posteriores do Windows com processos que você não possui, você deve iniciar o PowerShell com a opção Executar como administrador.

### Exemplo 8: localizar o proprietário de um processo

```powershell
Get-Process pwsh -IncludeUserName
```

```Output
Handles      WS(K)   CPU(s)     Id UserName            ProcessName
-------      -----   ------     -- --------            -----------
    782     132080     2.08   2188 DOMAIN01\user01     pwsh
```

Este comando mostra como localizar o proprietário de um processo.
No Windows, o parâmetro **IncludeUserName** requer direitos de usuário elevados (executar como administrador).
A saída revela que o proprietário é Domain01\user01.

### Exemplo 9: usar uma variável automática para identificar o processo que hospeda a sessão atual

```powershell
Get-Process pwsh
```

```Output
NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
------    -----      -----     ------      --  -- -----------
    83    96.21     105.95       4.33    1192  10 pwsh
    79    83.81     117.61       2.16   10580  10 pwsh
```

```powershell
Get-Process -Id $PID
```

```Output
NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
------    -----      -----     ------      --  -- -----------
    83    96.21      77.53       4.39    1192  10 pwsh
```

Esses comandos mostram como usar a `$PID` variável automática para identificar o processo que está hospedando a sessão atual do PowerShell. Você pode usar esse método para distinguir o processo de host de outros processos do PowerShell que talvez você queira parar ou fechar.

O primeiro comando obtém todos os processos do PowerShell na sessão atual.

O segundo comando obtém o processo do PowerShell que está hospedando a sessão atual.

### Exemplo 10: obter todos os processos que têm um título de janela principal e exibi-los em uma tabela

```powershell
Get-Process | Where-Object {$_.mainWindowTitle} | Format-Table Id, Name, mainWindowtitle -AutoSize
```

Esse comando obtém todos os processos que têm um título de janela principal e os exibe em uma tabela com a ID de processo e o nome do processo.

A propriedade **mainWindowTitle** é apenas uma das muitas propriedades úteis do objeto de **processo** que o `Get-Process` retorna. Para exibir todas as propriedades, redirecione os resultados de um `Get-Process` comando para o `Get-Member` cmdlet `Get-Process | Get-Member` .

## PARAMETERS

### -FileVersionInfo

Indica que esse cmdlet obtém as informações de versão de arquivo para o programa que é executado no processo.

No Windows Vista e versões posteriores do Windows, você deve abrir o PowerShell com a opção Executar como administrador para usar esse parâmetro em processos que não são de sua propriedade.

Para obter informações de versão do arquivo para um processo em um computador remoto, use o `Invoke-Command` cmdlet.

O uso desse parâmetro é equivalente a obter a propriedade **MainModule. FileVersionInfo** de cada objeto de processo. Quando você usa esse parâmetro, `Get-Process` retorna um **FileVersionInfo** objeto FileVersionInfo **System. Diagnostics. FileVersionInfo** , não um objeto de processo. Portanto, não é possível canalizar a saída do comando para um cmdlet que espera um objeto de processo, como `Stop-Process` .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Name, Id, InputObject
Aliases: FV, FVI

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Especifica um ou mais processos pela ID do processo (PID). Para especificar IDs múltiplas, use vírgulas para separá-las. Para localizar o PID de um processo, digite `Get-Process` .

```yaml
Type: System.Int32[]
Parameter Sets: Id, IdWithUserName
Aliases: PID

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IncludeUserName

Indica que o valor de nome de usuário do objeto de **processo** é retornado com os resultados do comando.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameWithUserName, IdWithUserName, InputObjectWithUserName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Especifica um ou mais objetos de processo. Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: InputObject, InputObjectWithUserName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Módulo

Indica que esse cmdlet obtém os módulos que foram carregados pelos processos.

No Windows Vista e versões posteriores do Windows, você deve abrir o PowerShell com a opção **Executar como administrador** para usar esse parâmetro em processos que não são de sua propriedade.

Para obter os módulos que foram carregados por um processo em um computador remoto, use o `Invoke-Command` cmdlet.

Esse parâmetro é equivalente a obter a propriedade **modules** de cada objeto de processo. Quando você usa esse parâmetro, esse cmdlet retorna um **ProcessModule** objeto ProcessModule **System. Diagnostics. ProcessModule** , não um objeto de processo. Portanto, não é possível canalizar a saída do comando para um cmdlet que espera um objeto de processo, como `Stop-Process` .

Quando você usa os parâmetros *Module* e **FileVersionInfo** no mesmo comando, esse cmdlet retorna um objeto **FileVersionInfo** com informações sobre a versão do arquivo de todos os módulos.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Name, Id, InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Especifica um ou mais processos pelo nome do processo. Você pode digitar vários nomes de processo (separados por vírgulas) e usar caracteres curinga. O nome do parâmetro ("Name") é opcional.

```yaml
Type: System.String[]
Parameter Sets: Name, NameWithUserName
Aliases: ProcessName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### System.Diagnostics.Process

É possível canalizar um objeto de processo para esse cmdlet.

## SAÍDAS

### System. Diagnostics. Process, System. Diagnostics. FileVersionInfo, System. Diagnostics. ProcessModule

Por padrão, esse cmdlet retorna um objeto **System. Diagnostics. Process** . Se você usar o parâmetro **FileVersionInfo** , ele retornará um objeto **System. Diagnostics. FileVersionInfo** . Se você usar o parâmetro **Module** , sem o parâmetro **FileVersionInfo** , ele retornará um objeto **System. Diagnostics. ProcessModule** .

## OBSERVAÇÕES

- Você também pode se referir a esse cmdlet por seus aliases internos, PS e GPS. Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).
- Em computadores que executam uma versão de 64 bits do Windows, a versão de 64 bits do PowerShell obtém apenas módulos de processo de 64 bits e a versão de 32 bits do PowerShell obtém apenas módulos de processo de 32 bits.
- Você pode usar as propriedades e métodos do objeto Instrumentação de Gerenciamento do Windows (WMI) Win32_Process no PowerShell. Para obter informações, consulte `Get-WmiObject` e o SDK do WMI.
- A exibição padrão de um processo é uma tabela que inclui as colunas a seguir. Para obter uma descrição de todas as propriedades de objetos de processo, consulte [Propriedades do processo](/dotnet/api/system.diagnostics.process).
  - Handles: o número de identificadores que o processo abriu.
  - NPM (K): a quantidade de memória não paginável que o processo está usando, em quilobytes.
  - PM (K): a quantidade de memória paginável que o processo está usando, em quilobytes.
  - WS (K): o tamanho do conjunto de trabalho do processo, em quilobytes.
    O conjunto de trabalho consiste de páginas de memória que foram referenciadas recentemente pelo processo.
  - VM (M): a quantidade de memória virtual que o processo está usando, em megabytes.
    Memória virtual inclui armazenamento nos arquivos de paginação em disco.
  - CPU (s): a quantidade de tempo do processador que o processo usou em todos os processadores, em segundos.
  - ID: a ID do processo (PID) do processo.
  - ProcessName: o nome do processo. Para obter explicações sobre os conceitos relacionados aos processos, consulte o Glossário na Ajuda e no Centro de Suporte e a Ajuda do Gerenciador de Tarefas.
- Você também pode usar as exibições alternativas internas dos processos disponíveis com, como `Format-Table` **StartTime** e **Priority** , e pode criar suas próprias exibições.

## LINKS RELACIONADOS

[Debug-Process](Debug-Process.md)

[Get-Process](Get-Process.md)

[Start-Process](Start-Process.md)

[Stop-Process](Stop-Process.md)

[Wait-Process](Wait-Process.md)
