---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-html?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Html
ms.openlocfilehash: 21ef51476ccee8efc5c7c13d273ef8a7811f33c4
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2020
ms.locfileid: "93195150"
---
# ConvertTo-Html

## SINOPSE
Converte objetos .NET em HTML que pode ser exibido em um navegador da Web.

## SYNTAX

### Página (padrão)

```
ConvertTo-Html [-InputObject <PSObject>] [[-Property] <Object[]>] [[-Body] <String[]>]
 [[-Head] <String[]>] [[-Title] <String>] [-As <String>] [-CssUri <Uri>] [-PostContent <String[]>]
 [-PreContent <String[]>] [-Meta <Hashtable>] [-Charset <String>] [-Transitional]
 [<CommonParameters>]
```

### Fragmento

```
ConvertTo-Html [-InputObject <PSObject>] [[-Property] <Object[]>] [-As <String>] [-Fragment]
 [-PostContent <String[]>] [-PreContent <String[]>] [<CommonParameters>]
```

## DESCRIPTION

O `ConvertTo-Html` cmdlet converte objetos .net em HTML que podem ser exibidos em um navegador da Web. Você pode usar este cmdlet para exibir a saída de um comando em uma página da Web.

Você pode usar os parâmetros de `ConvertTo-Html` para selecionar Propriedades de objeto, para especificar um formato de tabela ou lista, para especificar o título da página HTML, para adicionar texto antes e depois do objeto, e para retornar apenas a tabela ou fragmento de lista, em vez de uma página DTD estrita.

Quando você envia vários objetos para `ConvertTo-Html` o, o PowerShell cria a tabela (ou lista) com base nas propriedades do primeiro objeto que você enviar. Se os objetos restantes não tiverem uma das propriedades especificadas, o valor da propriedade do objeto será uma célula vazia. Se os objetos restantes têm propriedades adicionais, os valores de propriedade não são incluídos no arquivo.

## EXEMPLOS

### Exemplo 1: criar uma página da Web para exibir a data

```powershell
ConvertTo-Html -InputObject (Get-Date)
```

Este comando cria uma página HTML que exibe as propriedades da data atual. Ele usa o parâmetro **InputObject** para enviar os resultados de um `Get-Date` comando para o `ConvertTo-Html` cmdlet.

### Exemplo 2: criar uma página da Web para exibir aliases do PowerShell

```powershell
Get-Alias | ConvertTo-Html | Out-File aliases.htm
Invoke-Item aliases.htm
```

Este comando cria uma página HTML que lista os aliases do PowerShell no console atual.

O comando usa o `Get-Alias` cmdlet para obter os aliases. Ele usa o operador de pipeline ( `|` ) para enviar os aliases para o `ConvertTo-Html` cmdlet, que cria a página HTML. O comando também usa o `Out-File` cmdlet para enviar o código HTML para o `aliases.htm` arquivo.

### Exemplo 3: criar uma página da Web para exibir eventos do PowerShell

```powershell
`Get-EventLog` -LogName "Windows PowerShell" | ConvertTo-Html | Out-File pslog.htm
```

Este comando cria uma página HTML chamada `pslog.htm` que exibe os eventos no log de eventos do Windows PowerShell no computador local.

Ele usa o `Get-EventLog` cmdlet para obter os eventos no log do Windows PowerShell e, em seguida, usa o operador de pipeline ( `|` ) para enviar os eventos para o `ConvertTo-Html` cmdlet. O comando também usa o `Out-File` cmdlet para enviar o código HTML para o `pslog.htm` arquivo.

O comando também usa o `Out-File` cmdlet para enviar o código HTML para o `pslog.htm` arquivo.

### Exemplo 4: criar uma página da Web para exibir processos

```powershell
Get-Process |
  ConvertTo-Html -Property Name, Path, Company -Title "Process Information" |
    Out-File proc.htm
Invoke-Item proc.htm
```

Esses comandos criam e abrem uma página HTML que lista o nome, o caminho e a empresa dos processos no computador local.

O primeiro comando usa o `Get-Process` cmdlet para obter objetos que representam os processos em execução no computador. O comando usa o operador de pipeline ( `|` ) para enviar os objetos de processo para o `ConvertTo-Html` cmdlet.

O comando usa o parâmetro **Property** para selecionar três propriedades dos objetos de processo a serem incluídos na tabela. O comando usa o parâmetro **title** para especificar um título para a página HTML. O comando também usa o `Out-File` cmdlet para enviar o HTML resultante para um arquivo chamado Proc.htm.

O segundo comando usa o `Invoke-Item` cmdlet para abrir o `Proc.htm` no navegador padrão.

### Exemplo 5: criar uma página da Web para exibir objetos de serviço

```powershell
Get-Service | ConvertTo-Html -CssUri "test.css"
```

```Output
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"  "https://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
<html>
<head>
<title>HTML TABLE</title>
<link rel="stylesheet" type="text/css" href="test.css" />
...
```

Este comando cria uma página HTML dos objetos de serviço que o `Get-Service` cmdlet retorna. O comando usa o parâmetro **CssUri** para especificar uma folha de estilos em cascata para a página HTML.

O parâmetro **CssUri** adiciona uma `<link rel="stylesheet" type="text/css" href="test.css">` marca adicional ao HTML resultante. O atributo HREF na marca contém o nome da folha de estilos.

### Exemplo 6: criar uma página da Web para exibir objetos de serviço

```powershell
Get-Service | ConvertTo-Html -As LIST | Out-File services.htm
```

Este comando cria uma página HTML dos objetos de serviço que o `Get-Service` cmdlet retorna. O comando usa o **parâmetro as** para especificar um formato de lista. O cmdlet `Out-File` envia o HTML resultante para o `Services.htm` arquivo.

### Exemplo 7: criar uma tabela da Web para a data atual

```powershell
Get-Date | ConvertTo-Html -Fragment
```

```Output
<table>
<colgroup>...</colgroup>
<tr><th>DisplayHint</th><th>DateTime</th><th>Date</th><th>Day</th><th>DayOfWeek</th><th>DayOfYear</th><th>Hour</th>
<th>Kind</th><th>Millisecond</th><th>Minute</th><th>Month</th><th>Second</th><th>Ticks</th><th>TimeOfDay</th><th>Year</th></tr>
<tr><td>DateTime</td><td>Monday, May 05, 2008 10:40:04 AM</td><td>5/5/2008 12:00:00 AM</td><td>5</td><td>Monday</td>
<td>126</td><td>10</td><td>Local</td><td>123</td><td>40</td><td>5</td><td>4</td><td>633455808041237213</td><td>10:40:04.12
37213</td><td>2008</td></tr>
</table>
```

Esse comando usa `ConvertTo-Html` para gerar uma tabela HTML da data atual. O comando usa o `Get-Date` cmdlet para obter a data atual. Ele usa um operador de pipeline (|) para enviar os resultados para o `ConvertTo-Html` cmdlet.

O `ConvertTo-Html` comando inclui o parâmetro **Fragment** , que limita a saída a uma tabela HTML. Como resultado, os outros elementos de uma página HTML, como as marcas `<HEAD>` e `<BODY>`, são omitidos.

### Exemplo 8: criar uma página da Web para exibir eventos do PowerShell

```powershell
Get-EventLog -Log "Windows PowerShell" | ConvertTo-Html -Property id, level, task
```

Esse comando usa o `Get-EventLog` cmdlet para obter eventos do log de eventos do Windows PowerShell.

Ele usa um operador de pipeline ( `|` ) para enviar os eventos para o `ConvertTo-Html` cmdlet, que converte os eventos em formato HTML.

O `ConvertTo-Html` comando usa o parâmetro **Property** para selecionar apenas as propriedades **ID** , **Level** e **Task** do evento.

### Exemplo 9: criar uma página da Web para exibir os serviços especificados

```powershell
$htmlParams = @{
  Title = "Windows Services: Server01"
  Body = Get-Date
  PreContent = "<P>Generated by Corporate IT</P>"
  PostContent = "For details, contact Corporate IT."
}
Get-Service A* |
  ConvertTo-Html @htmlParams |
    Out-File Services.htm
Invoke-Item Services.htm
```

Esse comando cria e abre uma página da Web que exibe os serviços no computador que começam com um. Ele usa os parâmetros **título** , **corpo** , **PreContent** e **anticontent** de `ConvertTo-Html` para personalizar a saída.

A primeira parte do comando usa o `Get-Service` cmdlet para obter os serviços no computador que começam com um. O comando usa um operador de pipeline ( `|` ) para enviar os resultados para o `ConvertTo-Html` cmdlet. O comando também usa o `Out-File` cmdlet para enviar a saída para o arquivo de Services.htm.

Um ponto e vírgula ( `;` ) termina o primeiro comando e inicia um segundo comando, que usa o `Invoke-Item` cmdlet para abrir o `Services.htm` arquivo no navegador padrão.

### Exemplo 10: definir as propriedades meta e o conjunto de caracteres do HTML

```powershell
Get-Service | ConvertTo-HTML -Meta @{
  refresh=10
  author="Author's Name"
  keywords="PowerShell, HTML, ConvertTo-HTML"
} -Charset "UTF-8"
```

Este comando cria o HTML para uma página da Web com as marcas meta para atualização, autor e palavras-chave.
O conjunto de caracteres da página está definido como UTF-8

### Exemplo 11: definir o HTML como DTD de transição XHTML

```powershell
Get-Service | ConvertTo-HTML -Transitional
```

Este comando define o DOCTYPE do HTML retornado para o DTD de transição XHTML

## PARAMETERS

### -Como

Determina se o objeto é formatado como uma tabela ou uma lista. Os valores válidos são **tabela** e **lista** . O valor padrão é **Table** .

O valor da **tabela** gera uma tabela HTML que se assemelha ao formato de tabela do PowerShell. A linha de cabeçalho exibe os nomes de propriedade. Cada linha da tabela representa um objeto e exibe os valores do objeto para cada propriedade.

O valor da **lista** gera uma tabela HTML de duas colunas para cada objeto que se assemelha ao formato de lista do PowerShell. A primeira coluna exibe o nome da propriedade. A segunda coluna exibe o valor da propriedade.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Table, List

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Corpo

Especifica o texto a ser adicionado após a marca de abertura `<BODY>`. Por padrão, não há nenhum texto nessa posição.

```yaml
Type: System.String[]
Parameter Sets: Page
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Conjunto de caracteres

Especifica o texto a ser adicionado à `<charset>` marca de abertura. Por padrão, não há nenhum texto nessa posição.

Esse parâmetro foi introduzido no PowerShell 6,0.

```yaml
Type: System.String
Parameter Sets: Page
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CssUri

Especifica o Uniform Resource Identifier (URI) da folha de estilos em cascata (CSS) que é aplicada ao arquivo HTML. O URI é incluído em um link de folha de estilos na saída.

```yaml
Type: System.Uri
Parameter Sets: Page
Aliases: cu, uri

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Fragmento

Gera apenas uma tabela de HTML. As marcas HTML, HEAD, TITLE e BODY são omitidas.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Fragment
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cabeçalho

Especifica o conteúdo da marca `<HEAD>`. O padrão é `<title\>HTML TABLE</title>`. Se você usar o parâmetro **Head** , o parâmetro **title** será ignorado.

```yaml
Type: System.String[]
Parameter Sets: Page
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Especifica os objetos a serem representadas em HTML. Insira uma variável que contém os objetos ou digite um comando ou uma expressão que obtém os objetos.

Se você usar esse parâmetro para enviar vários objetos, como todos os serviços em um computador, `ConvertTo-Html` o criará uma tabela que exibe as propriedades de uma coleção ou de uma matriz de objetos. Para criar uma tabela de objetos individuais, use o operador de pipeline para canalizar os objetos `ConvertTo-Html` .

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

### -Meta

Especifica o texto a ser adicionado à `<meta>` marca de abertura. Por padrão, não há nenhum texto nessa posição.

Esse parâmetro foi introduzido no PowerShell 6,0.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: Page
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -O conteúdo

Especifica o texto a ser adicionado após a marca de fechamento `</TABLE>`. Por padrão, não há nenhum texto nessa posição.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PreContent

Especifica o texto a ser adicionado após a marca de abertura `<TABLE>`. Por padrão, não há nenhum texto nessa posição.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Propriedade

Inclui as propriedades especificadas dos objetos no HTML. O valor do parâmetro **Property** pode ser uma nova propriedade calculada. A propriedade calculada pode ser um bloco de script ou uma tabela de hash. Os pares de chave-valor válidos são:

- Nome (ou rótulo) – `<string>` (adicionado no PowerShell 6. x)
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
Accept wildcard characters: False
```

### -Title

Especifica um título para o arquivo HTML, ou seja, o texto que aparece entre as marcas `<TITLE>`.

```yaml
Type: System.String
Parameter Sets: Page
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Transicional

Altera o **DOCTYPE** para **DTD de transição XHTML** , o **DOCTYPE** padrão é um **DTD estrito de XHTML** .

Esse parâmetro foi introduzido no PowerShell 6,0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Page
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

Você pode canalizar qualquer objeto .NET para `ConvertTo-Html` .

## SAÍDAS

### Documento System. String ou System.Xml.Xml

`ConvertTo-Html` Retorna uma série de cadeias de caracteres que compõem um HTML válido.

## OBSERVAÇÕES

Para usar esse cmdlet, redirecione um ou mais objetos para o cmdlet ou use o parâmetro **InputObject** para especificar o objeto. Quando a entrada consiste em vários objetos, a saída desses dois métodos é bastante diferente.

- Quando você canaliza vários objetos para um cmdlet, o PowerShell envia os objetos para o cmdlet um de cada vez. Como resultado, `ConvertTo-Html` o cria uma tabela que exibe os objetos individuais. Por exemplo, se você canalizar os processos em um computador para `ConvertTo-Html` , a tabela resultante exibirá todos os processos.

- Quando você usa o parâmetro **InputObject** para enviar vários objetos, `ConvertTo-Html` o recebe esses objetos como uma coleção ou como uma matriz. Como resultado, ele cria uma tabela que exibe a matriz e suas propriedades, não os itens na matriz. Por exemplo, se você usar **InputObject** para enviar os processos em um computador para `ConvertTo-Html` , a tabela resultante exibirá uma matriz de objetos e suas propriedades.

  Para obedecer ao DTD estrito de XHTML, a marca DOCTYPE é modificada de acordo:

   `<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"   "https://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd"\>`

## LINKS RELACIONADOS

[about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[ConvertTo-Csv](ConvertTo-Csv.md)

[ConvertTo-Json](ConvertTo-Json.md)

[ConvertTo-Xml](ConvertTo-Xml.md)

[Export-Clixml](Export-Clixml.md)

[Import-Clixml](Import-Clixml.md)
