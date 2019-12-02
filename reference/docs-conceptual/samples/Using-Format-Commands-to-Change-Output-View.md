---
ms.date: 11/22/2019
keywords: powershell, cmdlet
title: Usando comandos de formatação para alterar a exibição de saída
ms.openlocfilehash: f270d5ec5efe5caf506d6a8a45285990996f6ae6
ms.sourcegitcommit: d43f66071f1f33b350d34fa1f46f3a35910c5d24
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74417594"
---
# <a name="using-format-commands-to-change-output-view"></a>Usando comandos de formatação para alterar a exibição de saída

O PowerShell tem um conjunto de cmdlets que permite controlar como as propriedades são exibidas para objetos específicos. Os nomes de todos os cmdlets começam com o verbo `Format`. Eles permitem que você selecione quais propriedades deseja mostrar.

```powershell
Get-Command -Verb Format -Module Microsoft.PowerShell.Utility
```

```Output
CommandType     Name               Version    Source
-----------     ----               -------    ------
Cmdlet          Format-Custom      6.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Format-Hex         6.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Format-List        6.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Format-Table       6.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Format-Wide        6.1.0.0    Microsoft.PowerShell.Utility
```

Este artigo descreve os cmdlets `Format-Wide`, `Format-List` e `Format-Table`.

Cada tipo de objeto no PowerShell tem propriedades padrão que são usadas quando você não especifica quais propriedades devem ser exibidas. Cada cmdlet também usa o mesmo parâmetro **Property** para especificar quais propriedades você deseja exibir. Como `Format-Wide` mostra uma única propriedade, seu parâmetro **Property** tem apenas um único valor, mas os parâmetros de propriedade de `Format-List` e `Format-Table` aceitam uma lista de nomes de propriedade.

Neste exemplo, a saída padrão do cmdlet `Get-Process` mostra que há duas instâncias do Internet Explorer em execução.

```powershell
Get-Process -Name iexplore
```

O formato padrão para objetos **Process** exibe as propriedades mostradas aqui:

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     32    25.52      10.25      13.11   12808   1 iexplore
     52    11.46      26.46       3.55   21748   1 iexplore
```

## <a name="using-format-wide-for-single-item-output"></a>Usando Format-Wide para saída Single-Item

O cmdlet `Format-Wide`, por padrão, exibe apenas a propriedade padrão de um objeto. As informações associadas a cada objeto são exibidas em uma única coluna:

```powershell
Get-Command -Verb Format | Format-Wide
```

```Output
Format-Custom          Format-Hex
Format-List            Format-Table
Format-Wide
```

Você também pode especificar uma propriedade não padrão:

```powershell
Get-Command -Verb Format | Format-Wide -Property Noun
```

```Output
Custom                 Hex
List                   Table
Wide
```

### <a name="controlling-format-wide-display-with-column"></a>Controlando a exibição Format-Wide com Column

Com o cmdlet `Format-Wide`, só é possível exibir uma única propriedade de cada vez. Isso o torna útil para exibir listas grandes em várias colunas.

```powershell
Get-Command -Verb Format | Format-Wide -Property Noun -Column 3
```

```Output
Custom                 Hex                  List
Table                  Wide

```

## <a name="using-format-list-for-a-list-view"></a>Usando Format-List para uma exibição de lista

O cmdlet `Format-List` exibe um objeto em forma de uma listagem, com cada propriedade rotulada e exibida em uma linha separada:

```powershell
Get-Process -Name iexplore | Format-List
```

```Output
Id      : 12808
Handles : 578
CPU     : 13.140625
SI      : 1
Name    : iexplore

Id      : 21748
Handles : 641
CPU     : 3.59375
SI      : 1
Name    : iexplore
```

Você pode especificar quantas propriedades quiser:

```powershell
Get-Process -Name iexplore | Format-List -Property ProcessName,FileVersion,StartTime,Id
```

```Output
ProcessName : iexplore
FileVersion : 11.00.18362.1 (WinBuild.160101.0800)
StartTime   : 10/22/2019 11:23:58 AM
Id          : 12808

ProcessName : iexplore
FileVersion : 11.00.18362.1 (WinBuild.160101.0800)
StartTime   : 10/22/2019 11:23:57 AM
Id          : 21748
```

### <a name="getting-detailed-information-by-using-format-list-with-wildcards"></a>Obtendo informações detalhadas usando Format-List com curingas

O cmdlet `Format-List` permite usar um caractere curinga como o valor do parâmetro **Property**. Isso permite exibir informações detalhadas. Geralmente, os objetos incluem mais informações do que você precisa, por isso, o PowerShell não mostra todos os valores de propriedade por padrão. Para mostrar todas as propriedades de um objeto, use o comando `Format-List -Property *`. O comando a seguir gera mais de 60 linhas de saída para um único processo:

```powershell
Get-Process -Name iexplore | Format-List -Property *
```

Embora o comando `Format-List` seja útil para mostrar os detalhes, se você quiser obter uma visão geral de saída que inclui vários itens, uma exibição de tabela simples geralmente será mais útil.

## <a name="using-format-table-for-tabular-output"></a>Usando Format-Table para saída tabular

Caso você use o cmdlet `Format-Table` sem nenhum nome de propriedade especificado para formatar a saída do comando `Get-Process`, obterá exatamente a mesma saída que receberia sem um cmdlet `Format`. Por padrão, o PowerShell exibe objetos **Process** em um formato tabular.

```powershell
Get-Service -Name win* | Format-Table
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  WinDefend          Windows Defender Antivirus Service
Running  WinHttpAutoProx... WinHTTP Web Proxy Auto-Discovery Se...
Running  Winmgmt            Windows Management Instrumentation
Running  WinRM              Windows Remote Management (WS-Manag...
```

### <a name="improving-format-table-output-autosize"></a>Melhorando a saída do Format-Table (AutoSize)

Embora uma exibição tabular seja útil para exibir muitas informações, ela poderá ser difícil de interpretar se a exibição for muito estreita para os dados. No exemplo anterior, a saída está truncada. Se você especificar o parâmetro **AutoSize** ao executar o comando `Format-Table`, o PowerShell calculará as larguras das colunas com base nos dados reais exibidos. Isso torna as colunas legíveis.

```powershell
Get-Service -Name win* | Format-Table -AutoSize
```

```Output
Status  Name                DisplayName
------  ----                -----------
Running WinDefend           Windows Defender Antivirus Service
Running WinHttpAutoProxySvc WinHTTP Web Proxy Auto-Discovery Service
Running Winmgmt             Windows Management Instrumentation
Running WinRM               Windows Remote Management (WS-Management)
```

O cmdlet `Format-Table` ainda pode truncar os dados, mas trunca apenas no final da tela. Propriedades, além da última exibida, recebem o tamanho correspondente ao que precisam para seu elemento de dados mais longo ser exibido corretamente.

```powershell
Get-Service -Name win* | Format-Table -Property Name,Status,StartType,DisplayName,DependentServices -AutoSize
```

```Output
Name                 Status StartType DisplayName                               DependentServi
                                                                                ces
----                 ------ --------- -----------                               --------------
WinDefend           Running Automatic Windows Defender Antivirus Service        {}
WinHttpAutoProxySvc Running    Manual WinHTTP Web Proxy Auto-Discovery Service  {NcaSvc, iphl…
Winmgmt             Running Automatic Windows Management Instrumentation        {vmms, TPHKLO…
WinRM               Running Automatic Windows Remote Management (WS-Management) {}
```

O comando `Format-Table` assume que as propriedades são listadas em ordem de importância. Portanto, ele tenta exibir completamente as propriedades mais próximas do início. Se o comando `Format-Table` não puder exibir todas as propriedades, ele removerá algumas colunas da exibição. Você pode ver esse comportamento na propriedade **DependentServices** do exemplo anterior.

### <a name="wrapping-format-table-output-in-columns-wrap"></a>Quebra automática de linha na saída de Format-Table em colunas (Wrap)

Você pode forçar dados do `Format-Table` longos a serem encapsulados em sua coluna de exibição usando o parâmetro **Wrap**. Usar o parâmetro **Wrap** pode não fazer o que você espera, já que ele usará as configurações padrão se você não especificar **AutoSize**:

```powershell
Get-Service -Name win* | Format-Table -Property Name,Status,StartType,DisplayName,DependentServices -Wrap
```

```Output
Name                 Status StartType DisplayName                               DependentServi
                                                                                ces
----                 ------ --------- -----------                               --------------
WinDefend           Running Automatic Windows Defender Antivirus Service        {}
WinHttpAutoProxySvc Running    Manual WinHTTP Web Proxy Auto-Discovery Service  {NcaSvc,
                                                                                iphlpsvc}
Winmgmt             Running Automatic Windows Management Instrumentation        {vmms,
                                                                                TPHKLOAD,
                                                                                SUService,
                                                                                smstsmgr…}
WinRM               Running Automatic Windows Remote Management (WS-Management) {}
```

Usar o parâmetro **Wrap** por si só não deixa o processamento muito mais lento. No entanto, usar **AutoSize** para formatar uma lista de arquivos recursivos de uma estrutura de diretório grande pode levar muito tempo e usar muita memória antes de exibir os primeiros itens de saída.

Se você não estiver preocupado com a carga do sistema, **AutoSize** funcionará bem com o parâmetro **Wrap**.
As colunas iniciais ainda usam a largura necessária para exibir itens em uma linha, mas a coluna final é quebrada, caso necessário.

> [!NOTE]
> Algumas colunas podem não ser exibidas quando você especifica as colunas mais largas primeiro. Para obter melhores resultados, especifique os elementos de dados menores primeiro.

No exemplo a seguir, especificamos as propriedades mais amplas primeiro.

```powershell
Get-Process -Name iexplore | Format-Table -Wrap -AutoSize -Property FileVersion,Path,Name,Id
```

Mesmo com a quebrar de linha, a coluna **Id** final é omitida:

```Output
FileVersion                          Path                                                  Nam
                                                                                           e
-----------                          ----                                                  ---
11.00.18362.1 (WinBuild.160101.0800) C:\Program Files (x86)\Internet Explorer\IEXPLORE.EXE iex
                                                                                           plo
                                                                                           re
11.00.18362.1 (WinBuild.160101.0800) C:\Program Files\Internet Explorer\iexplore.exe       iex
                                                                                           plo
                                                                                           re
```

### <a name="organizing-table-output--groupby"></a>Organizando a saída da tabela (-GroupBy)

Outro parâmetro útil para controlar a saída tabular é **GroupBy**. Listagens de tabela mais longas podem ser especialmente difíceis de comparar. O parâmetro **GroupBy** agrupa a saída com base em um valor da propriedade. Por exemplo, podemos agrupar serviços por **StartType** para uma inspeção mais fácil, omitindo o valor **StartType** da listagem de propriedades:

```powershell
Get-Service -Name win* | Sort-Object StartType | Format-Table -GroupBy StartType
```

```Output
   StartType: Automatic
Status   Name               DisplayName
------   ----               -----------
Running  WinDefend          Windows Defender Antivirus Service
Running  Winmgmt            Windows Management Instrumentation
Running  WinRM              Windows Remote Management (WS-Managem…

   StartType: Manual
Status   Name               DisplayName
------   ----               -----------
Running  WinHttpAutoProxyS… WinHTTP Web Proxy Auto-Discovery Serv…
```
