---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-string?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-String
ms.openlocfilehash: 665a0ca8332c4052b59362c7947e408ba811c5f2
ms.sourcegitcommit: c4906f4c9fa4ef1a16dcd6dd00ff960d19446d71
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "93195283"
---
# ConvertFrom-String

## SINOPSE
Extrai e analisa as propriedades estruturadas do conteúdo da cadeia de caracteres.

## SYNTAX

### ByDelimiter (padrão)

```
ConvertFrom-String [-Delimiter <String>] [-PropertyNames <String[]>] [-InputObject] <String>
 [<CommonParameters>]
```

### TemplateParsing

```
ConvertFrom-String [-TemplateFile <String[]>] [-TemplateContent <String[]>] [-IncludeExtent] [-UpdateTemplate]
 [-InputObject] <String> [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **ConvertFrom-String** extrai e analisa as propriedades estruturadas do conteúdo da cadeia de caracteres.
Esse cmdlet gera um objeto analisando o texto de um fluxo de texto tradicional.
Para cada cadeia de caracteres no pipeline, o cmdlet divide a entrada por um delimitador ou uma expressão de análise e atribui nomes de propriedade a cada um dos elementos de divisão resultantes.
Você pode fornecer esses nomes de propriedade; Se você não fizer isso, eles serão gerados automaticamente para você.

O conjunto de parâmetros padrão do cmdlet, **ByDelimiter** , é dividido exatamente no delimitador de expressão regular.
Ele não executa a correspondência de aspas ou a saída de delimitador conforme o `Import-Csv` cmdlet faz.

O conjunto de parâmetros alternativo do cmdlet, **TemplateParsing** , gera elementos dos grupos que são capturados por uma expressão regular. Para obter mais informações sobre expressões regulares, consulte [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).

Esse cmdlet dá suporte a dois modos: análise delimitada básica e análise automaticamente gerada por exemplo.

A análise delimitada, por padrão, divide a entrada no espaço em branco e atribui nomes de propriedade aos grupos resultantes.

Você pode personalizar o delimitador canalizando os `ConvertFrom-String` resultados em um dos `Format-*` cmdlets ou pode usar o parâmetro **delimitador** .

O cmdlet também dá suporte à análise orientada por exemplo gerada automaticamente, com base no [FlashExtract, trabalho de pesquisa da Microsoft Research](https://www.microsoft.com/research/publication/flashextract-framework-data-extraction-examples/).

## EXEMPLOS

### Exemplo 1: gerar um objeto com nomes de propriedade padrão

```powershell
"Hello World" | ConvertFrom-String
```

```Output
P1    P2
--    --
Hello World
```

Esse comando gera um objeto com nomes de propriedade padrão, **P1** e **P2** .

### Exemplo 1A: Conheça o objeto gerado

Esse comando gera um objeto com as propriedades **P1** , **P2** ; as duas propriedades são do tipo **cadeia de caracteres** , por padrão.

```powershell
"Hello World" | ConvertFrom-String | Get-Member
```

```Output

   TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
P1          NoteProperty string P1=Hello
P2          NoteProperty string P2=World
```

### Exemplo 2: gerar um objeto com nomes de propriedade padrão usando um delimitador

Esse comando gera um objeto com um domínio e um nome de usuário usando a barra invertida ( `\` ) como o delimitador. O caractere de barra invertida deve ter um escape com outra barra invertida ao usar expressões regulares.

```powershell
"Contoso\Administrator" | ConvertFrom-String -Delimiter "\\"
```

```Output
P1      P2
--      --
Contoso Administrator
```

### Exemplo 3: gerar um objeto que contém duas propriedades nomeadas

O exemplo a seguir cria objetos de entradas de arquivo de hosts do Windows.

```powershell
$content = Get-Content C:\Windows\System32\drivers\etc\hosts
$content = $content -match "^[^#]"
$content | ConvertFrom-String -PropertyNames IP, Server
```

```Output
IP             Server
--             ------
192.168.7.10   W2012R2
192.168.7.20   W2016
192.168.7.101  WIN8
192.168.7.102  WIN10
```

O `Get-Content` cmdlet armazena o conteúdo de um arquivo de hosts do Windows no `$content` . O segundo comando Remove todos os comentários no início do arquivo de hosts usando uma expressão regular que corresponde a qualquer linha que não comece com ( `#` ). O último comando converte o texto restante em objetos com propriedades de **servidor** e **IP** .

### Exemplo 4: Use uma expressão como o valor do parâmetro TemplateContent, salve os resultados em uma variável.

Esse comando usa uma expressão como o valor do parâmetro **TemplateContent** .
A expressão é salva em uma variável para simplificar.
O Windows PowerShell agora compreende que a cadeia de caracteres usada no pipeline `ConvertFrom-String` tem três propriedades:

- **Nome**
- **phone**
- **age**

```powershell
$template = @'
{Name*:Phoebe Cat}, {phone:425-123-6789}, {age:6}
{Name*:Lucky Shot}, {phone:(206) 987-4321}, {age:12}
'@

$testText = @'
Phoebe Cat, 425-123-6789, 6
Lucky Shot, (206) 987-4321, 12
Elephant Wise, 425-888-7766, 87
Wild Shrimp, (111)  222-3333, 1
'@

$PersonalData = $testText | ConvertFrom-String -TemplateContent $template
Write-output ("Pet items found: " + ($PersonalData.Count))
$PersonalData
```

```Output
Pet items found: 4

Name          phone           age
----          -----           ---
Phoebe Cat    425-123-6789    6
Lucky Shot    (206) 987-4321  12
Elephant Wise 425-888-7766    87
Wild Shrimp   (111)  222-3333 1
```

Cada linha na entrada é avaliada pelas correspondências de exemplo. Se a linha corresponder aos exemplos fornecidos no padrão, os valores serão extraídos e passados para a variável de saída.

Os dados de exemplo, `$template` , fornecem dois formatos de telefone diferentes:

- `425-123-6789`
- `(206) 987-4321`

Os dados de exemplo também fornecem dois formatos de idade diferentes:

- `6`
- `12`

Isso implica que telefones como `(206) 987 4321` não serão reconhecidos, porque não há nenhum dado de exemplo que corresponda a esse padrão porque não há hifens.

### Exemplo 5: especificando tipos de dados para as propriedades geradas

Este é o mesmo exemplo do exemplo 4 acima.
A diferença é que a cadeia de caracteres de padrão inclui um tipo de dados para cada propriedade desejada.

```powershell
$template = @'
{[string]Name*:Phoebe Cat}, {[string]phone:425-123-6789}, {[int]age:6}
{[string]Name*:Lucky Shot}, {[string]phone:(206) 987-4321}, {[int]age:12}
'@

$testText = @'
Phoebe Cat, 425-123-6789, 6
Lucky Shot, (206) 987-4321, 12
Elephant Wise, 425-888-7766, 87
Wild Shrimp, (111)  222-3333, 1
'@

$PersonalData = $testText | ConvertFrom-String -TemplateContent $template
Write-output ("Pet items found: " + ($PersonalData.Count))
$PersonalData
```

```Output
Pet items found: 4

Name          phone           age
----          -----           ---
Phoebe Cat    425-123-6789      6
Lucky Shot    (206) 987-4321   12
Elephant Wise 425-888-7766     87
Wild Shrimp   (111)  222-3333   1
```

```powershell
$PersonalData | Get-Member
```

```Output
   TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
age         NoteProperty int age=6
Name        NoteProperty string Name=Phoebe Cat
phone       NoteProperty string phone=425-123-6789
```

O `Get-Member` cmdlet é usado para mostrar que a propriedade **age** é um inteiro.

## PARAMETERS

### -Delimitador

Especifica uma expressão regular que identifica o limite entre os elementos.
Elementos que são criados pela divisão se tornam propriedades no objeto resultante.
O delimitador é usado basicamente em uma chamada para o método **Split** do tipo `[System.Text.RegularExpressions.RegularExpression]` .

```yaml
Type: System.String
Parameter Sets: ByDelimiter
Aliases: DEL

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeExtent

Indica que esse cmdlet inclui uma propriedade de texto de extensão que é removida por padrão.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TemplateParsing
Aliases: IE

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Especifica cadeias de caracteres recebidas do pipeline ou uma variável que contém um objeto de cadeia de caracteres.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PropertyNames

Especifica uma matriz de nomes de propriedade para a qual atribuir valores de divisão no objeto resultante.
Cada linha de texto que você divide ou analisa gera elementos que representam valores de propriedade.
Se o elemento for o resultado de um grupo de captura e esse grupo de captura for nomeado (por exemplo, `(?<name>)` ou `(?'name')` ), o nome desse grupo de captura será atribuído à propriedade.

Se você fornecer quaisquer elementos na matriz **PropertyName** , esses nomes serão atribuídos às propriedades que ainda não foram nomeadas.

Se você fornecer mais nomes de Propriedade do que os campos, o PowerShell ignorará os nomes de propriedade extras. Se você não especificar nomes de propriedade suficientes para nomear todos os campos, o PowerShell atribuirá automaticamente nomes de propriedade numérica a quaisquer propriedades que não estejam nomeadas: **P1** , **P2** , etc.

```yaml
Type: System.String[]
Parameter Sets: ByDelimiter
Aliases: PN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TemplateContent

Especifica uma expressão ou uma expressão salva como uma variável, que descreve as propriedades para as quais esse cmdlet atribui cadeias de caracteres. A sintaxe de uma especificação de campo de modelo é a seguinte: `{[optional-typecast]<name>:<example-value>}` .

```yaml
Type: System.String[]
Parameter Sets: TemplateParsing
Aliases: TC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TemplateFile

Especifica um arquivo, como uma matriz, que contém um modelo para a análise desejada da cadeia de caracteres.
No arquivo de modelo, as propriedades e seus valores são colocados entre colchetes, conforme mostrado abaixo.
Se uma propriedade, como a propriedade **Name** e suas outras propriedades associadas, aparecer várias vezes, você poderá adicionar um asterisco ( `*` ) para indicar que isso resulta em vários registros. Isso evita a extração de várias propriedades em um único registro.

```
{Name*:David Chew}
{City:Redmond}, {State:WA}
{Name*:Evan Narvaez}    {Name*:Antonio Moreno}
{City:Issaquah}, {State:WA}
```

```yaml
Type: System.String[]
Parameter Sets: TemplateParsing
Aliases: TF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Updatetemplate

Indica que esse cmdlet salva os resultados de um algoritmo de aprendizado em um comentário no arquivo de modelo.
Isso torna o processo de aprendizado de algoritmo mais rápido.
Para usar esse parâmetro, você também deve especificar um arquivo de modelo com o parâmetro **TemplateFile** .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TemplateParsing
Aliases: UT

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Esse cmdlet oferece suporte aos parâmetros comuns:,,,,,, `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` e `-WarningVariable` . Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### System.String

## SAÍDAS

## OBSERVAÇÕES

## LINKS RELACIONADOS

[ConvertFrom-cadeia de caracteres: análise de texto baseada em exemplo](https://devblogs.microsoft.com/powershell/convertfrom-string-example-based-text-parsing/)

[ConvertFrom-StringData](ConvertFrom-StringData.md)

[ConvertFrom-Csv](ConvertFrom-Csv.md)

[ConvertTo-Xml](ConvertTo-Xml.md)
