---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/select-object?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Select-Object
ms.openlocfilehash: 59cbba88e3c21d740b774d95e7c0e734cd8e3fdc
ms.sourcegitcommit: f9ae48d026d65833b9c8ca881058dda0bbd067b4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2020
ms.locfileid: "93195359"
---
# Select-Object

## SINOPSE
Seleciona objetos ou propriedades de objeto.

## SYNTAX

### Defaultparameter (padrão)

```
Select-Object [-InputObject <PSObject>] [[-Property] <Object[]>] [-ExcludeProperty <String[]>]
 [-ExpandProperty <String>] [-Unique] [-Last <Int32>] [-First <Int32>] [-Skip <Int32>] [-Wait]
 [<CommonParameters>]
```

### SkipLastParameter

```
Select-Object [-InputObject <PSObject>] [[-Property] <Object[]>] [-ExcludeProperty <String[]>]
 [-ExpandProperty <String>] [-Unique] [-SkipLast <Int32>] [<CommonParameters>]
```

### IndexParameter

```
Select-Object [-InputObject <PSObject>] [-Unique] [-Wait] [-Index <Int32[]>] [<CommonParameters>]
```

## DESCRIPTION

O `Select-Object` cmdlet seleciona as propriedades especificadas de um objeto ou conjunto de objetos. Ele também pode selecionar objetos únicos, um número especificado de objetos, ou então objetos em uma posição especificada em uma matriz.

Para selecionar objetos de uma coleção, use os parâmetros **First** , **Last** , **Unique** , **Skip** e **Index** . Para selecionar as propriedades do objeto, use o parâmetro **Property** . Quando você seleciona propriedades, o `Select-Object` retorna novos objetos que têm apenas as propriedades especificadas.

A partir do Windows PowerShell 3,0, `Select-Object` o inclui um recurso de otimização que impede que os comandos criem e processem objetos que não são usados.

Quando você inclui um `Select-Object` comando com os parâmetros **First** ou **index** em um pipeline de comando, o PowerShell interrompe o comando que gera os objetos assim que o número selecionado de objetos é gerado, mesmo quando o comando que gera os objetos é exibido antes do `Select-Object` comando no pipeline. Para desativar esse comportamento de otimização, use o parâmetro **Wait** .

## EXEMPLOS

### Exemplo 1: selecionar objetos por Propriedade

Este exemplo cria objetos que têm as propriedades de **nome** , **ID** e conjunto de trabalho ( **WS** ) de objetos de processo.

```powershell
Get-Process | Select-Object -Property ProcessName, Id, WS
```

### Exemplo 2: selecionar objetos por propriedade e formatar os resultados

Este exemplo obtém informações sobre os módulos usados pelos processos no computador. Ele usa `Get-Process` o cmdlet para obter o processo no computador.

Ele usa o `Select-Object` cmdlet para gerar uma matriz de `[System.Diagnostics.ProcessModule]` instâncias, conforme contido na propriedade **modules** de cada `System.Diagnostics.Process` saída de instância por `Get-Process` .

O parâmetro **Property** do `Select-Object` cmdlet seleciona os nomes dos processos. Isso adiciona uma `ProcessName` **notaproperty** a cada `[System.Diagnostics.ProcessModule]` instância e a popula com o valor da propriedade **ProcessName** do processo atual.

Por fim, `Format-List` o cmdlet é usado para exibir o nome e os módulos de cada processo em uma lista.

```powershell
Get-Process Explorer | Select-Object -Property ProcessName -ExpandProperty Modules | Format-List
```

```Output
ProcessName       : explorer
ModuleName        : explorer.exe
FileName          : C:\WINDOWS\explorer.exe
BaseAddress       : 140697278152704
ModuleMemorySize  : 3919872
EntryPointAddress : 140697278841168
FileVersionInfo   : File:             C:\WINDOWS\explorer.exe
                    InternalName:     explorer
                    OriginalFilename: EXPLORER.EXE.MUI
                    FileVersion:      10.0.17134.1 (WinBuild.160101.0800)
                    FileDescription:  Windows Explorer
                    Product:          Microsoft Windows Operating System
                    ProductVersion:   10.0.17134.1
...
```

### Exemplo 3: selecionar processos usando a maior parte da memória

Este exemplo obtém os cinco processos que estão usando a maior parte da memória. O `Get-Process` cmdlet obtém os processos no computador. O `Sort-Object` cmdlet classifica os processos de acordo com o uso de memória (conjunto de trabalho) e o `Select-Object` cmdlet seleciona apenas os últimos cinco membros da matriz de objetos resultante.

O parâmetro **Wait** não é necessário em comandos que incluem o `Sort-Object` cmdlet porque o `Sort-Object` processa todos os objetos e, em seguida, retorna uma coleção. A `Select-Object` otimização está disponível apenas para comandos que retornam objetos individualmente à medida que são processados.

```powershell
Get-Process | Sort-Object -Property WS | Select-Object -Last 5
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VS(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
2866     320       33432      45764   203   222.41   1292 svchost
577      17        23676      50516   265    50.58   4388 WINWORD
826      11        75448      76712   188    19.77   3780 Ps
1367     14        73152      88736   216    61.69    676 Ps
1612     44        66080      92780   380   900.59   6132 INFOPATH
```

### Exemplo 4: selecionar caracteres exclusivos de uma matriz

Este exemplo usa o parâmetro **exclusivo** de `Select-Object` para obter caracteres exclusivos de uma matriz de caracteres.

```powershell
"a","b","c","a","a","a" | Select-Object -Unique
```

```Output
a
b
c
```

### Exemplo 5: selecionar eventos mais recentes e mais antigos no log de eventos

Este exemplo obtém os primeiros (mais recentes) e os últimos eventos (mais antigos) no log de eventos do Windows PowerShell.

`Get-EventLog` Obtém todos os eventos no log do Windows PowerShell e os salva na `$a` variável.
Em seguida, `$a` é canalizado para o `Select-Object` cmdlet. O `Select-Object` comando usa o parâmetro **index** para selecionar eventos da matriz de eventos na `$a` variável. O índice do primeiro evento é 0. O índice do último evento é o número de itens em `$a` menos 1.

```powershell
$a = Get-EventLog -LogName "Windows PowerShell"
$a | Select-Object -Index 0, ($A.count - 1)
```

### Exemplo 6: selecionar tudo, exceto o primeiro objeto

Este exemplo cria uma nova PSSession em cada um dos computadores listados na Servers.txt arquivos, exceto para o primeiro.

`Select-Object` seleciona tudo, exceto o primeiro computador em uma lista de nomes de computador. A lista de computadores resultante é definida como o valor do parâmetro **ComputerName** do `New-PSSession` cmdlet.

```powershell
New-PSSession -ComputerName (Get-Content Servers.txt | Select-Object -Skip 1)
```

### Exemplo 7: renomear arquivos e selecionar vários para revisão

Este exemplo adiciona um sufixo "-ro" aos nomes base dos arquivos de texto que têm o atributo somente leitura e, em seguida, exibe os cinco primeiros arquivos para que o usuário possa ver uma amostra do efeito.

`Get-ChildItem` usa o parâmetro dinâmico **ReadOnly** para obter arquivos somente leitura. Os arquivos resultantes são canalizados para o `Rename-Item` cmdlet, que renomeia o arquivo. Ele usa o parâmetro **PassThru** do `Rename-Item` para enviar os arquivos renomeados para o `Select-Object` cmdlet, que seleciona os primeiros 5 para exibição.

O parâmetro **Wait** de `Select-Object` impede que o PowerShell interrompa o `Get-ChildItem` cmdlet depois de obter os primeiros cinco arquivos de texto somente leitura. Sem este parâmetro, somente os primeiros cinco arquivos somente leitura devem ser renomeados.

```powershell
Get-ChildItem *.txt -ReadOnly |
    Rename-Item -NewName {$_.BaseName + "-ro.txt"} -PassThru |
    Select-Object -First 5 -Wait
```

### Exemplo 8: demonstrar as complexidades do parâmetro-ExpandProperty

Este exemplo demonstra as complexidades do parâmetro **ExpandProperty** .

Observe que a saída gerada foi uma matriz de `[System.Int32]` instâncias. As instâncias estão em conformidade com as regras de formatação padrão da **exibição de saída** . Isso é verdadeiro para todas as propriedades *expandidas* . Se os objetos enviados tiverem um formato padrão específico, a propriedade expandida poderá não estar visível.

```powershell
# Create a custom object to use for the Select-Object example.
$object = [pscustomobject]@{Name="CustomObject";Expand=@(1,2,3,4,5)}
# Use the ExpandProperty parameter to Expand the property.
$object | Select-Object -ExpandProperty Expand -Property Name
```

```Output
1
2
3
4
5
```

```powershell
# The output did not contain the Name property, but it was added successfully.
# Use Get-Member to confirm the Name property was added and populated.
$object | Select-Object -ExpandProperty Expand -Property Name | Get-Member
```

```Output
   TypeName: System.Int32

Name        MemberType   Definition
----        ----------   ----------
CompareTo   Method       int CompareTo(System.Object value), int CompareTo(int value), int IComparable.CompareTo(System.Object obj)...
Equals      Method       bool Equals(System.Object obj), bool Equals(int obj), bool IEquatable[int].Equals(int other)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
GetTypeCode Method       System.TypeCode GetTypeCode(), System.TypeCode IConvertible.GetTypeCode()
ToBoolean   Method       bool IConvertible.ToBoolean(System.IFormatProvider provider)
ToByte      Method       byte IConvertible.ToByte(System.IFormatProvider provider)
ToChar      Method       char IConvertible.ToChar(System.IFormatProvider provider)
ToDateTime  Method       datetime IConvertible.ToDateTime(System.IFormatProvider provider)
ToDecimal   Method       decimal IConvertible.ToDecimal(System.IFormatProvider provider)
ToDouble    Method       double IConvertible.ToDouble(System.IFormatProvider provider)
ToInt16     Method       int16 IConvertible.ToInt16(System.IFormatProvider provider)
ToInt32     Method       int IConvertible.ToInt32(System.IFormatProvider provider)
ToInt64     Method       long IConvertible.ToInt64(System.IFormatProvider provider)
ToSByte     Method       sbyte IConvertible.ToSByte(System.IFormatProvider provider)
ToSingle    Method       float IConvertible.ToSingle(System.IFormatProvider provider)
ToString    Method       string ToString(), string ToString(string format), string ToString(System.IFormatProvider provider)...
ToType      Method       System.Object IConvertible.ToType(type conversionType, System.IFormatProvider provider)
ToUInt16    Method       uint16 IConvertible.ToUInt16(System.IFormatProvider provider)
ToUInt32    Method       uint32 IConvertible.ToUInt32(System.IFormatProvider provider)
ToUInt64    Method       uint64 IConvertible.ToUInt64(System.IFormatProvider provider)
Name        NoteProperty string Name=CustomObject
```

### Exemplo 9: criar propriedades personalizadas em objetos

O exemplo a seguir demonstra `Select-Object` como usar o para adicionar uma propriedade personalizada a qualquer objeto.
Quando você especifica um nome de propriedade que não existe, o `Select-Object` cria essa propriedade como uma **observaçãoproperty** em cada objeto passado.

```powershell
$customObject = 1 | Select-Object -Property MyCustomProperty
$customObject.MyCustomProperty = "New Custom Property"
$customObject
```

```Output
MyCustomProperty
----------------
New Custom Property
```

### Exemplo 10: criar propriedades calculadas para cada InputObject

Este exemplo demonstra `Select-Object` como usar o para adicionar propriedades calculadas à sua entrada. Passar um **scriptblock** para o parâmetro **Property** faz com que o `Select-Object` avalie a expressão em cada objeto passado e adicione os resultados à saída. Dentro do **scriptblock** , você pode usar a `$_` variável para fazer referência ao objeto atual no pipeline.

Por padrão, `Select-Object` o usará a cadeia de **scriptblock** como o nome da propriedade. Usando uma **tabela de hash** , você pode rotular a saída do **scriptblock** como uma propriedade personalizada adicionada a cada objeto. Você pode adicionar várias propriedades calculadas a cada objeto passado para `Select-Object` .

```powershell
# Create a calculated property called $_.StartTime.DayOfWeek
Get-Process | Select-Object -Property ProcessName,{$_.StartTime.DayOfWeek}
```

```Output
ProcessName  $_.StartTime.DayOfWeek
----         ----------------------
alg                       Wednesday
ati2evxx                  Wednesday
ati2evxx                   Thursday
...
```

```powershell
# Add a custom property to calculate the size in KiloBytes of each FileInfo object you pass in.
# Use the pipeline variable to divide each file's length by 1 KiloBytes
$size = @{label="Size(KB)";expression={$_.length/1KB}}
# Create an additional calculated property with the number of Days since the file was last accessed.
# You can also shorten the key names to be 'l', and 'e', or use Name instead of Label.
$days = @{l="Days";e={((Get-Date) - $_.LastAccessTime).Days}}
# You can also shorten the name of your label key to 'l' and your expression key to 'e'.
Get-ChildItem $PSHOME -File | Select-Object Name, $size, $days
```

```Output
Name                        Size(KB)        Days
----                        --------        ----
Certificate.format.ps1xml   12.5244140625   223
Diagnostics.Format.ps1xml   4.955078125     223
DotNetTypes.format.ps1xml   134.9833984375  223
```

## PARAMETERS

### -ExcludeProperty

Especifica as propriedades que esse cmdlet exclui da operação. Caracteres curinga são permitidos. Este parâmetro é efetivo somente quando o comando também inclui o parâmetro **Property** .

```yaml
Type: System.String[]
Parameter Sets: DefaultParameter, SkipLastParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -ExpandProperty

Especifica uma propriedade a selecionar e indica que deve-se tentar expandir essa propriedade.

- Se a propriedade especificada for uma matriz, cada valor da matriz será incluído na saída.
- Se a propriedade especificada for um objeto, as propriedades de objetos serão expandidas para cada **InputObject**

Em ambos os casos, o **tipo** de saída de objetos corresponderá ao **tipo** da propriedade expandida.

Se o parâmetro **Property** for especificado, o `Select-Object` tentará adicionar cada propriedade selecionada como uma **NoteProperty** a cada objeto de saída.

> [!WARNING]
> Se você receber o erro: SELECT: a propriedade não pode ser processada porque `<PropertyName>` a propriedade já existe, considere o seguinte.
> Observe que, ao `-ExpandProperty` usar `Select-Object` o, não é possível substituir uma propriedade existente.
> Isso significa:
>
> - Se o objeto expandido tiver uma propriedade de mesmo nome, ocorrerá um erro.
> - Se o objeto *selecionado* tiver uma propriedade de mesmo nome que uma propriedade de objetos *expandida* , ocorrerá um erro.

```yaml
Type: System.String
Parameter Sets: DefaultParameter, SkipLastParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Primeiro

Especifica o número de objetos a selecionar desde o início de uma matriz de objetos de entrada.

```yaml
Type: System.Int32
Parameter Sets: DefaultParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Índice

Seleciona objetos de uma matriz com base nos valores de índice desses objetos. Digite os índices separados por vírgulas em uma lista. Os índices em uma matriz começam com 0, onde 0 representa o primeiro valor e (n-1) representa o último valor.

```yaml
Type: System.Int32[]
Parameter Sets: IndexParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Especifica os objetos a enviar ao cmdlet pelo pipeline. Esse parâmetro permite canalizar objetos para o `Select-Object` .

Quando você passa objetos para o parâmetro **InputObject** , em vez de usar o pipeline, `Select-Object` o trata o **InputObject** como um único objeto, mesmo que o valor seja uma coleção. É recomendável que você use o pipeline ao passar coleções para o `Select-Object` .

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

### -Último

Especifica o número de objetos a selecionar desde o final de uma matriz de objetos de entrada.

```yaml
Type: System.Int32
Parameter Sets: DefaultParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Propriedade

Especifica as propriedades a selecionar. Essas propriedades são adicionadas como membros da **observaçãoproperty** aos objetos de saída. Caracteres curinga são permitidos.

O valor do parâmetro **Property** pode ser uma nova propriedade calculada. Para criar uma propriedade calculada, use uma tabela de hash.

As chaves válidas são:

- Nome (ou rótulo)- `<string>`
- Expressão- `<string>` ou `<script block>`

Para obter mais informações, consulte [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).

```yaml
Type: System.Object[]
Parameter Sets: DefaultParameter, SkipLastParameter
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Ignorar

Ignora (não seleciona) o número de itens especificado. Por padrão, o parâmetro **Skip** conta a partir do início da matriz ou da lista de objetos, mas se o comando usar o **último** parâmetro, ele contará do final da lista ou da matriz.

Ao contrário do parâmetro **Index** , que inicia a contagem em 0, o parâmetro **Skip** começa em 1.

```yaml
Type: System.Int32
Parameter Sets: DefaultParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipLast

Ignora (não seleciona) o número especificado de itens do final da lista ou da matriz. Funciona da mesma maneira que o uso de **Skip** junto com o **último** parâmetro.

Ao contrário do parâmetro de **índice** , que inicia a contagem em 0, o parâmetro **SkipLast** começa em 1.

```yaml
Type: System.Int32
Parameter Sets: SkipLastParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Exclusivo

Especifica que, se um subconjunto dos objetos de entrada tem valores e propriedades idênticos, apenas um único membro do subconjunto será selecionado.

Este parâmetro diferencia maiúsculas e minúsculas. Como resultado, cadeias de caracteres que diferem apenas em maiúsculas e minúsculas são consideradas como sendo exclusivas.

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

### -Wait

Indica que o cmdlet desativa a otimização. O PowerShell executa comandos na ordem em que aparecem no pipeline de comando e permite que eles gerem todos os objetos. Por padrão, se você incluir um `Select-Object` comando com os parâmetros **First** ou **index** em um pipeline de comando, o PowerShell interromperá o comando que gera os objetos assim que o número selecionado de objetos for gerado.

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DefaultParameter, IndexParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### System. Management. Automation. PSObject

Você pode canalizar qualquer objeto para `Select-Object` .

## SAÍDAS

### System. Management. Automation. PSObject

## OBSERVAÇÕES

- Você também pode se referir ao `Select-Object` cmdlet por seu alias interno, `select` . Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

- O recurso de otimização do `Select-Object` está disponível apenas para comandos que gravam objetos no pipeline conforme eles são processados. Esse recurso não tem nenhum efeito em comandos que armazenam objetos processados em buffer e gravam-nos como uma coleção de comandos. Gravar objetos imediatamente é uma prática recomendada para design de cmdlets. Para obter mais informações, consulte _gravar registros únicos no pipeline_ em [diretrizes de desenvolvimento altamente incentivadas](/powershell/scripting/developer/windows-powershell).

## LINKS RELACIONADOS

[about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[Group-Object](Group-Object.md)

[Sort-Object](Sort-Object.md)

[Where-Object](../Microsoft.PowerShell.Core/Where-Object.md)
