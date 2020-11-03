---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/compare-object?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Compare-Object
ms.openlocfilehash: 994bed44d9632ad836f204ceafd6c7493591b91a
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "93196634"
---
# Compare-Object

## Sinopse
Compara dois conjuntos de objetos.

## Sintaxe

```
Compare-Object [-ReferenceObject] <PSObject[]> [-DifferenceObject] <PSObject[]>
 [-SyncWindow <Int32>] [-Property <Object[]>] [-ExcludeDifferent] [-IncludeEqual] [-PassThru]
 [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

## Descrição

O `Compare-Object` cmdlet compara dois conjuntos de objetos. Um conjunto de objetos é a **referência** e o outro conjunto de objetos é a **diferença** .

`Compare-Object` verifica se há métodos disponíveis para comparar um objeto inteiro. Se não for possível encontrar um método adequado, ele chamará os métodos **ToString ()** dos objetos de entrada e comparará os resultados da cadeia de caracteres. Você pode fornecer uma ou mais propriedades a serem usadas para comparação. Quando as propriedades são fornecidas, o cmdlet compara os valores dessas propriedades apenas.

O resultado da comparação indica se um valor de propriedade apareceu somente no objeto de **referência** ( `<=` ) ou somente no objeto de **diferença** ( `=>` ). Se o parâmetro **includeequal** for usado, ( `==` ) indicará que o valor está em ambos os objetos.

Se a **referência** ou os objetos de **diferença** forem nulos ( `$null` ), o `Compare-Object` gerará um erro de encerramento.

Alguns exemplos usam nivelamento para reduzir o tamanho da linha dos exemplos de código. Para obter mais informações, consulte [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).

## Exemplos

### Exemplo 1 – comparar o conteúdo de dois arquivos de texto

Este exemplo compara o conteúdo de dois arquivos de texto. O exemplo usa os dois arquivos de texto a seguir, com cada valor em uma linha separada.

- `Testfile1.txt` contém os valores: Dog, Squirrel e pássaro.
- `Testfile2.txt` contém os valores: Cat, pássaro e racoon.

A saída exibe apenas as linhas que são diferentes entre os arquivos. `Testfile1.txt` é o objeto de **referência** ( `<=` ) e `Testfile2.txt` é o objeto de **diferença** ( `=>` ). Linhas com conteúdo que aparecem em ambos os arquivos não são exibidas.

```powershell
Compare-Object -ReferenceObject (Get-Content -Path C:\Test\Testfile1.txt) -DifferenceObject (Get-Content -Path C:\Test\Testfile2.txt)
```

```Output
InputObject SideIndicator
----------- -------------
cat         =>
racoon      =>
dog         <=
squirrel    <=
```

### Exemplo 2 – comparar cada linha de conteúdo e excluir as diferenças

Este exemplo usa os parâmetros **includeequal** e **ExcludeDifferent** para comparar cada linha de conteúdo em dois arquivos de texto.

Como o comando usa o parâmetro **ExcludeDifferent** , a saída contém apenas as linhas contidas em ambos os arquivos, conforme mostrado pelo **SideIndicator** ( `==` ).

```powershell
$objects = @{
  ReferenceObject = (Get-Content -Path C:\Test\Testfile1.txt)
  DifferenceObject = (Get-Content -Path C:\Test\Testfile2.txt)
}
Compare-Object @objects -IncludeEqual -ExcludeDifferent
```

```Output
InputObject SideIndicator
----------- -------------
bird        ==
```

<a id="ex3" />

### Exemplo 3-mostrar a diferença ao usar o parâmetro PassThru

Normalmente, `Compare-Object` retorna um tipo **PSCustomObject** com as seguintes propriedades:

- O **InputObject** que está sendo comparado
- A propriedade **SideIndicator** que mostra a qual objeto de entrada a saída pertence

Quando você usa o parâmetro **PassThru** , o **tipo** do objeto não é alterado, mas a instância do objeto retornado tem uma **observaçãoproperty** adicionada chamada **SideIndicator** . **SideIndicator** mostra a qual objeto de entrada a saída pertence.

Os exemplos a seguir mostram os diferentes tipos de saída.

```powershell
$a = $True
Compare-Object -IncludeEqual $a $a
(Compare-Object -IncludeEqual $a $a) | Get-Member
```

```Output
InputObject SideIndicator
----------- -------------
       True ==

   TypeName: System.Management.Automation.PSCustomObject
Name          MemberType   Definition
----          ----------   ----------
Equals        Method       bool Equals(System.Object obj)
GetHashCode   Method       int GetHashCode()
GetType       Method       type GetType()
ToString      Method       string ToString()
InputObject   NoteProperty System.Boolean InputObject=True
SideIndicator NoteProperty string SideIndicator===
```

```powershell
Compare-Object -IncludeEqual $a $a -PassThru
(Compare-Object -IncludeEqual $a $a -PassThru) | Get-Member
```

```Output
True

   TypeName: System.Boolean
Name          MemberType   Definition
----          ----------   ----------
CompareTo     Method       int CompareTo(System.Object obj), int CompareTo(bool value), int IComparable.CompareTo(Syst
Equals        Method       bool Equals(System.Object obj), bool Equals(bool obj), bool IEquatable[bool].Equals(bool ot
GetHashCode   Method       int GetHashCode()
GetType       Method       type GetType()
GetTypeCode   Method       System.TypeCode GetTypeCode(), System.TypeCode IConvertible.GetTypeCode()
ToBoolean     Method       bool IConvertible.ToBoolean(System.IFormatProvider provider)
ToByte        Method       byte IConvertible.ToByte(System.IFormatProvider provider)
ToChar        Method       char IConvertible.ToChar(System.IFormatProvider provider)
ToDateTime    Method       datetime IConvertible.ToDateTime(System.IFormatProvider provider)
ToDecimal     Method       decimal IConvertible.ToDecimal(System.IFormatProvider provider)
ToDouble      Method       double IConvertible.ToDouble(System.IFormatProvider provider)
ToInt16       Method       short IConvertible.ToInt16(System.IFormatProvider provider)
ToInt32       Method       int IConvertible.ToInt32(System.IFormatProvider provider)
ToInt64       Method       long IConvertible.ToInt64(System.IFormatProvider provider)
ToSByte       Method       sbyte IConvertible.ToSByte(System.IFormatProvider provider)
ToSingle      Method       float IConvertible.ToSingle(System.IFormatProvider provider)
ToString      Method       string ToString(), string ToString(System.IFormatProvider provider), string IConvertible.To
ToType        Method       System.Object IConvertible.ToType(type conversionType, System.IFormatProvider provider)
ToUInt16      Method       ushort IConvertible.ToUInt16(System.IFormatProvider provider)
ToUInt32      Method       uint IConvertible.ToUInt32(System.IFormatProvider provider)
ToUInt64      Method       ulong IConvertible.ToUInt64(System.IFormatProvider provider)
TryFormat     Method       bool TryFormat(System.Span[char] destination, [ref] int charsWritten)
SideIndicator NoteProperty string SideIndicator===
```

Ao usar **PassThru** , o tipo de objeto original ( **System. Boolean** ) é retornado. Observe como a saída exibida pelo formato padrão para objetos **System. Boolean** não exibia a propriedade **SideIndicator** . No entanto, o objeto **System. Boolean** retornado tem a **observaçãoproperty** adicionada.

### Exemplo 4 – comparar dois objetos simples usando propriedades

Neste exemplo, comparamos duas cadeias de caracteres diferentes que têm o mesmo comprimento.

```powershell
Compare-Object -ReferenceObject 'abc' -DifferenceObject 'xyz' -Property Length -IncludeEqual
```

```Output
Length SideIndicator
------ -------------
     3 ==
```

### Exemplo 5-comparando objetos complexos usando propriedades

Este exemplo mostra o comportamento ao comparar objetos complexos. Neste exemplo, armazenamos dois objetos de processo diferentes para diferentes instâncias do PowerShell. Ambas as variáveis contêm objetos de processo com o mesmo nome. Quando os objetos são comparados sem especificar o parâmetro **Property** , o cmdlet considera os objetos como iguais. Observe que o valor de **InputObject** é o mesmo que o resultado do método **ToString ()** . Como a classe **System. Diagnostics. Process** não tem a interface **IComparable** , o cmdlet converte os objetos em cadeias de caracteres e, em seguida, compara os resultados.

```powershell
PS> Get-Process pwsh

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    101   123.32     139.10      35.81   11168   1 pwsh
     89   107.55      66.97      11.44   17600   1 pwsh

PS> $a = Get-Process -Id 11168
PS> $b = Get-Process -Id 17600
PS> $a.ToString()
System.Diagnostics.Process (pwsh)
PS> $b.ToString()
System.Diagnostics.Process (pwsh)
PS> Compare-Object $a $b -IncludeEqual

InputObject                       SideIndicator
-----------                       -------------
System.Diagnostics.Process (pwsh) ==

PS> Compare-Object $a $b -Property ProcessName, Id, CPU

ProcessName    Id       CPU SideIndicator
-----------    --       --- -------------
pwsh        17600   11.4375 =>
pwsh        11168 36.203125 <=
```

Quando você especifica Propriedades a serem comparadas, o cmdlet mostra as diferenças.

### Exemplo 6 – comparando objetos complexos que implementam IComparable

Se o objeto implementar **IComparable** , o cmdlet pesquisará maneiras de comparar os objetos. Se os objetos forem de tipos diferentes, o objeto de **diferença** será convertido no tipo de **referenceobject** , em comparação.

Neste exemplo, estamos comparando uma cadeia de caracteres a um objeto **TimeSpan** . No primeiro caso, a cadeia de caracteres é convertida em um **TimeSpan** para que os objetos sejam iguais.

```powershell
Compare-Object ([TimeSpan]"0:0:1") "0:0:1" -IncludeEqual
```

```Output
InputObject SideIndicator
----------- -------------
00:00:01    ==
```

```powershell
Compare-Object "0:0:1" ([TimeSpan]"0:0:1")
```

```Output
InputObject SideIndicator
----------- -------------
00:00:01    =>
0:0:1       <=
```

No segundo caso, o **TimeSpan** é convertido em uma cadeia de caracteres para que o objeto seja diferente.

## Parâmetros

### -CaseSensitive

Indica que as comparações devem diferenciar maiúsculas de minúsculas.

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

### -Culture

Especifica a cultura a ser usada para as comparações.

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

### -Differenceobject

Especifica os objetos que são comparados aos objetos de **referência** .

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ExcludeDifferent

Indica que esse cmdlet exibe apenas as características dos objetos comparados que são iguais. As diferenças entre os objetos são descartadas.

Use **ExcludeDifferent** com **includeequal** para exibir apenas as linhas que correspondem entre os objetos de **referência** e **diferença** .

Se **ExcludeDifferent** for especificado sem **includeequal** , não haverá nenhuma saída.

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

### -IncludeEqual

**Includeequal** exibe as correspondências entre os objetos de **referência** e **diferença** .

Por padrão, a saída também inclui as diferenças entre os objetos de **referência** e **diferença** .

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

### -PassThru

Quando você usa o parâmetro **PassThru** , `Compare-Object` o omite o wrapper **PSCustomObject** em volta dos objetos comparados e retorna os objetos diferentes, inalterados.

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

### -Propriedade

Especifica uma matriz de propriedades dos objetos de **referência** e **diferença** a serem comparados.

O valor do parâmetro **Property** pode ser uma nova propriedade calculada. A propriedade calculada pode ser um bloco de script ou uma tabela de hash. Os pares de chave-valor válidos são:

- Expressão- `<string>` ou `<script block>`

Para obter mais informações, consulte [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Referenceobject

Especifica uma matriz de objetos usada como referência para comparação.

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SyncWindow

Especifica o número de objetos adjacentes que `Compare-Object` inspeciona ao procurar uma correspondência em uma coleção de objetos. `Compare-Object` examina objetos adjacentes quando não encontra o objeto na mesma posição em uma coleção. O valor padrão é `[Int32]::MaxValue` , que significa que `Compare-Object` o examina toda a coleção de objetos.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: [Int32]::MaxValue
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Entradas

### System. Management. Automation. PSObject

Você pode enviar um objeto para baixo do pipeline para o parâmetro **differenceobject** .

## Saídas

### Nenhum

Se o objeto de **referência** e o objeto de **diferença** forem os mesmos, não haverá nenhuma saída, a menos que você use o parâmetro **includeequal** .

### System. Management. Automation. PSCustomObject

Se os objetos forem diferentes, o `Compare-Object` encapsulará os objetos diferentes em um `PSCustomObject` wrapper com uma propriedade **SideIndicator** para fazer referência às diferenças.

Quando você usa o parâmetro **PassThru** , o **tipo** do objeto não é alterado, mas a instância do objeto retornado tem uma **observaçãoproperty** adicionada chamada **SideIndicator** . **SideIndicator** mostra a qual objeto de entrada a saída pertence.

## Observações

Ao usar o parâmetro **PassThru** , a saída exibida no console pode não incluir a propriedade **SideIndicator** . A exibição de formato padrão do para a saída do tipo de objeto por não `Compare-Object` inclui a propriedade **SideIndicator** . Para obter mais informações, consulte o [exemplo 3](#ex3) neste artigo.

## Links relacionados

[about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[ForEach-Object](../Microsoft.PowerShell.Core/ForEach-Object.md)

[Group-Object](Group-Object.md)

[Measure-Object](Measure-Object.md)

[New-Object](New-Object.md)

[Select-Object](Select-Object.md)

[Sort-Object](Sort-Object.md)

[Tee-Object](Tee-Object.md)

[Where-Object](../Microsoft.PowerShell.Core/Where-Object.md)

[Get-Process](../Microsoft.PowerShell.Management/Get-Process.md)
