---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-table?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Table
ms.openlocfilehash: 06f0573496f04d6790d7899afa5809ede720adee
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2020
ms.locfileid: "93195185"
---
# Format-Table

## SINOPSE
Formata a saída como uma tabela.

## SYNTAX

### Tudo

```
Format-Table [-AutoSize] [-RepeatHeader] [-HideTableHeaders] [-Wrap] [[-Property] <Object[]>]
 [-GroupBy <Object>] [-View <String>] [-ShowError] [-DisplayError] [-Force] [-Expand <String>]
 [-InputObject <PSObject>] [<CommonParameters>]
```

## DESCRIPTION

O `Format-Table` cmdlet formata a saída de um comando como uma tabela com as propriedades selecionadas do objeto em cada coluna. O tipo de objeto determina o layout padrão e as propriedades que são exibidas em cada coluna. Você pode usar o parâmetro **Property** para selecionar as propriedades que deseja exibir.

O PowerShell usa os formatadores padrão para definir como os tipos de objeto são exibidos. Você pode usar `.ps1xml` arquivos para criar modos de exibição personalizados que exibem uma tabela de saída com propriedades especificadas. Depois que um modo de exibição personalizado for criado, use o parâmetro **View** para exibir a tabela com o modo de exibição personalizado. Para obter mais informações sobre exibições, consulte [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).

Você pode usar uma tabela de hash para adicionar propriedades calculadas a um objeto antes de exibi-lo e especificar os títulos de coluna na tabela. Para adicionar uma propriedade calculada, use o parâmetro **Property** ou **GroupBy** . Para obter informações sobre tabelas de hash, confira [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).

## EXEMPLOS

### Exemplo 1: Formatar host do PowerShell

Este exemplo exibe informações sobre o programa host para o PowerShell em uma tabela.

```powershell
Get-Host | Format-Table -AutoSize
```

O `Get-Host` cmdlet obtém objetos **System. Management. Automation. Internal. host. InternalHost** que representam o host. Os objetos são enviados do pipeline para o `Format-Table` e exibidos em uma tabela. O parâmetro **AutoSize** ajusta as larguras das colunas para minimizar o truncamento.

### Exemplo 2: Formatar processos por BasePriority

Neste exemplo, os processos são exibidos em grupos que têm a mesma propriedade **BasePriority** .

```powershell
Get-Process | Sort-Object -Property BasePriority | Format-Table -GroupBy BasePriority -Wrap
```

O `Get-Process` cmdlet obtém objetos que representam cada processo no computador e os envia para o pipeline `Sort-Object` . Os objetos são classificados na ordem de sua propriedade **BasePriority** .

Os objetos classificados são enviados do pipeline para o `Format-Table` . O parâmetro **GroupBy** organiza os dados de processo em grupos com base no valor da propriedade **BasePriority** . O parâmetro **Wrap** garante que os dados não sejam truncados.

### Exemplo 3: Formatar processos por data de início

Este exemplo exibe informações sobre os processos em execução no computador. Os objetos são classificados e `Format-Table` usam uma exibição para agrupar os objetos pela data de início.

```powershell
Get-Process | Sort-Object StartTime | Format-Table -View StartTime
```

`Get-Process` Obtém os objetos **System. Diagnostics. Process** que representam os processos em execução no computador. Os objetos são enviados ao pipeline para `Sort-Object` e são classificados com base na propriedade **StartTime** .

Os objetos classificados são enviados do pipeline para o `Format-Table` . O parâmetro **View** especifica a exibição **StartTime** que é definida no arquivo do PowerShell `DotNetTypes.format.ps1xml` para **objetos System. Diagnostics. Process** . A exibição **StartTime** converte cada hora de início dos processos em uma data abreviada e, em seguida, agrupa os processos pela data de início.

O `DotNetTypes.format.ps1xml` arquivo contém uma exibição de **prioridade** para processos. Você pode criar seus próprios `format.ps1xml` arquivos com exibições personalizadas.

### Exemplo 4: usar uma exibição personalizada para a saída da tabela

Neste exemplo, uma exibição personalizada exibe o conteúdo de um diretório. A exibição personalizada adiciona a coluna **CreationTime** à saída da tabela para objetos **System. IO. DirectoryInfo** e **System. IO. FileInfo** criados pelo `Get-ChildItem` .

O modo de exibição personalizado neste exemplo foi criado a partir do modo de exibição definido no código-fonte do PowerShell. Para obter mais informações sobre exibições e o código usado para criar essa exibição de exemplo, consulte [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md#sample-xml-for-a-format-table-custom-view).

```powershell
Get-ChildItem  -Path C:\Test | Format-Table -View mygciview
```

```Output
    Directory: C:\Test

Mode                LastWriteTime              CreationTime         Length Name
----                -------------              ------------         ------ ----
d-----        11/4/2019     15:54       9/24/2019     15:54                Archives
d-----        8/27/2019     14:22       8/27/2019     14:22                Drawings
d-----       10/23/2019     09:38       2/25/2019     09:38                Files
-a----        11/7/2019     11:07       11/7/2019     11:07          11345 Alias.txt
-a----        2/27/2019     15:15       2/27/2019     15:15            258 alias_out.txt
-a----        2/27/2019     15:16       2/27/2019     15:16            258 alias_out2.txt
```

`Get-ChildItem` Obtém o conteúdo do diretório atual, `C:\Test` . Os objetos **System. IO. DirectoryInfo** e **System. IO. FileInfo** são enviados pelo pipeline.
`Format-Table` usa o parâmetro **View** para especificar a exibição personalizada **mygciview** que inclui a coluna **CreationTime** .

A `Format-Table` saída padrão para `Get-ChildItem` não inclui a coluna **CreationTime** .

### Exemplo 5: usar propriedades para saída de tabela

Este exemplo usa o parâmetro **Property** para exibir todos os serviços do computador em uma tabela de duas colunas que mostra o **nome** das propriedades e **DependentServices** .

```powershell
Get-Service | Format-Table -Property Name, DependentServices
```

`Get-Service` Obtém todos os serviços no computador e envia os objetos **System. ServiceProcess. ServiceController** para baixo do pipeline. `Format-Table` usa o parâmetro **Property** para especificar que as propriedades **Name** e **dependservices** são exibidas na tabela.

**Name** e **DependentServices** são duas das propriedades do tipo de objeto. Para exibir todas as propriedades: `Get-Service | Get-Member -MemberType Properties` .

### Exemplo 6: Formatar um processo e calcular seu tempo de execução

Este exemplo exibe uma tabela com o nome do processo e o tempo total de execução para os processos do **bloco de notas** do computador local. O tempo de execução total é calculado subtraindo-se a hora de início de cada processo da hora atual.

```powershell
Get-Process notepad |
  Format-Table ProcessName, @{Label="TotalRunningTime"; Expression={(Get-Date) - $_.StartTime}}
```

```Output
ProcessName TotalRunningTime
----------- ----------------
notepad     03:20:00.2751767
notepad     00:00:16.7710520
```

`Get-Process` Obtém todos os processos do **bloco de notas** do computador local e envia os objetos por meio do pipeline. `Format-Table` exibe uma tabela com duas colunas: **ProcessName** , uma `Get-Process` propriedade e **TotalRunningTime** , uma propriedade calculada.

A propriedade **TotalRunningTime** é especificada por uma tabela de hash com duas chaves, **rótulo** e **expressão** . A chave de **rótulo** especifica o nome da propriedade. A chave de **expressão** especifica o cálculo. A expressão Obtém a propriedade **StartTime** de cada objeto de processo e a subtrai do resultado de um `Get-Date` comando, que obtém a data e a hora atuais.

### Exemplo 7: Formatar processos do bloco de notas

Este exemplo usa `Get-CimInstance` para obter o tempo de execução para todos os processos do **bloco de notas** no computador local. Você pode usar `Get-CimInstance` com o parâmetro **ComputerName** para obter informações de computadores remotos.

```powershell
$Processes = Get-CimInstance -Class win32_process -Filter "name='notepad.exe'"
$Processes | Format-Table ProcessName, @{ Label = "Total Running Time"; Expression={(Get-Date) - $_.CreationDate}}
```

```Output
ProcessName Total Running Time
----------- ------------------
notepad.exe 03:39:39.6260693
notepad.exe 00:19:56.1376922
```

`Get-CimInstance` Obtém as instâncias da classe WMI **Win32_Process** que descreve todos os processos do computador local chamados **notepad.exe** . Os objetos de processo são armazenados na `$Processes` variável.

Os objetos de processo na `$Processes` variável são enviados ao pipeline para `Format-Table` , que exibe a propriedade **ProcessName** e uma nova propriedade calculada, **tempo total de execução** .

O comando atribui o nome da nova propriedade calculada, **tempo total de execução** , à chave do **rótulo** . O bloco de script da chave de **expressão** calcula quanto tempo o processo está em execução subtraindo a data de criação dos processos a partir da data atual. O `Get-Date` cmdlet obtém a data atual. A data de criação é subtraída da data atual. O resultado é o valor do **tempo total de execução** .

### Exemplo 8: erros de formato de solução de problemas

Os exemplos a seguir mostram os resultados da adição dos parâmetros **DisplayError** ou **exerror** com uma expressão.

```powershell
Get-Date | Format-Table DayOfWeek,{ $_ / $null } -DisplayError
```

```Output
DayOfWeek  $_ / $null
--------- ------------
Wednesday #ERR
```

```powershell
Get-Date | Format-Table DayOfWeek,{ $_ / $null } -ShowError
```

```Output
DayOfWeek  $_ / $null
--------- ------------
Wednesday
Failed to evaluate expression " $_ / $null ".
+ CategoryInfo          : InvalidArgument: (11/27/2019 12:52:38:PSObject) [], RuntimeException
+ FullyQualifiedErrorId : PSPropertyExpressionError
```

## PARAMETERS

### -AutoSize

Indica que o cmdlet ajusta o tamanho da coluna e o número de colunas com base na largura dos dados. Por padrão, o número de colunas e seu tamanho são determinados pelo modo de exibição.

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

### -DisplayError

Indica que o cmdlet exibe erros na linha de comando. Esse parâmetro pode ser usado como um auxílio de depuração quando você estiver Formatando expressões em um `Format-Table` comando e precisar solucionar problemas das expressões.

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

### -Expandir

Especifica o formato do objeto de coleção e os objetos na coleção. Esse parâmetro é projetado para formatar objetos que dão suporte à interface [ICollection](/dotnet/api/system.collections.icollection) ([System. Collections](/dotnet/api/system.collections)). O valor padrão é **EnumOnly** .
Os valores aceitáveis para esse parâmetro são os seguintes:

- **EnumOnly** : exibe as propriedades dos objetos na coleção.
- **CoreOnly** : exibe as propriedades do objeto de coleção.
- **Ambos** : exibe as propriedades do objeto de coleção e as propriedades de objetos na coleção.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CoreOnly, EnumOnly, Both

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Indica que o cmdlet direciona o cmdlet para exibir todas as informações de erro. Use com o parâmetro **DisplayError** ou **exerror** . Por padrão, quando um objeto de erro é gravado para os fluxos de erro ou de exibição, apenas algumas das informações de erro são exibidas.

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

### -GroupBy

Especifica a saída classificada em tabelas separadas com base em um valor de propriedade. Por exemplo, você pode usar **GroupBy** para listar os serviços em tabelas separadas com base em seu status.

Insira uma expressão ou uma propriedade. O parâmetro **GroupBy** espera que os objetos sejam classificados.
Use o `Sort-Object` cmdlet antes de usar o `Format-Table` para agrupar os objetos.

O valor do parâmetro **GroupBy** pode ser uma nova propriedade calculada. A propriedade calculada pode ser um bloco de script ou uma tabela de hash. Os pares de chave-valor válidos são:

- Nome (ou rótulo)- `<string>`
- Expressão- `<string>` ou `<script block>`
- FormatString `<string>`

Para obter mais informações, consulte [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HideTableHeaders

Omite os cabeçalhos de coluna da tabela.

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

Especifica os objetos a serem formatados. Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.

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

Especifica as propriedades do objeto que aparecem na exibição e a ordem em que aparecem. Digite um ou mais nomes de propriedade, separados por vírgulas, ou use uma tabela de hash para exibir uma propriedade calculada. Caracteres curinga são permitidos.

Se você omitir esse parâmetro, as propriedades exibidas na exibição dependerão das propriedades do primeiro objeto. Por exemplo, se o primeiro objeto tiver **propertya** e **PropertyB** , mas os objetos subsequentes tiverem **propertya** , **PropertyB** e **PropertyC** , somente os cabeçalhos **propertya** e **PropertyB** serão exibidos.

O parâmetro **Property** é opcional. Você não pode usar os parâmetros **Property** e **View** no mesmo comando.

O valor do parâmetro **Property** pode ser uma nova propriedade calculada. A propriedade calculada pode ser um bloco de script ou uma tabela de hash. Os pares de chave-valor válidos são:

- Nome (ou rótulo) `<string>`
- Expressão- `<string>` ou `<script block>`
- FormatString `<string>`
- Largura- `<int32>` -deve ser maior que `0`
- Alinhamento-o valor pode ser `Left` , `Center` ou `Right`

Para obter mais informações, consulte [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -RepeatHeader

Repete a exibição do cabeçalho de uma tabela depois de cada tela cheia. O cabeçalho repetido é útil quando a saída é canalizada para um pager, como `less` ou `more` ou paginação com um leitor de tela.

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

### -Erro

Esse parâmetro envia erros por meio do pipeline. Esse parâmetro pode ser usado como um auxílio de depuração quando você estiver Formatando expressões em um `Format-Table` comando e precisar solucionar problemas das expressões.

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

### -Exibição

A partir do PowerShell 6, as exibições padrão são definidas no `C#` código-fonte do PowerShell. Os `*.format.ps1xml` arquivos do powershell 5,1 e versões anteriores não existem no PowerShell 6 e versões posteriores.

O parâmetro **View** permite especificar um formato alternativo ou uma exibição personalizada para a tabela. Você pode usar os modos de exibição padrão do PowerShell ou criar modos de exibição personalizados. Para obter mais informações sobre como criar uma exibição personalizada, consulte [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).

As exibições alternativas e personalizadas para o parâmetro de **exibição** devem usar o formato de tabela, caso contrário, `Format-Table` falhará. Se a exibição alternativa for uma lista, use o `Format-List` cmdlet. Se a exibição alternativa não for uma lista ou uma tabela, use o `Format-Custom` cmdlet.

Você não pode usar os parâmetros **Property** e **View** no mesmo comando.

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

### -Encapsulamento

Exibe na linha seguinte o texto que excede a largura da coluna. Por padrão, o texto que excede a largura da coluna é truncado.

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

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Management. Automation. PSObject

Você pode enviar qualquer objeto para baixo do pipeline para `Format-Table` .

## SAÍDAS

### Microsoft. PowerShell. Commands. Internal. Format

`Format-Table` retorna objetos de formato que representam a tabela.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md)

[about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[Export-FormatData](Export-FormatData.md)

[Format-Custom](Format-Custom.md)

[Format-Hex](Format-Hex.md)

[Format-List](Format-List.md)

[Format-Wide](Format-Wide.md)

[Get-FormatData](Get-FormatData.md)

[Get-Member](Get-Member.md)

[Get-CimInstance](../CimCmdlets/Get-CimInstance.md)

[Update-FormatData](Update-FormatData.md)
