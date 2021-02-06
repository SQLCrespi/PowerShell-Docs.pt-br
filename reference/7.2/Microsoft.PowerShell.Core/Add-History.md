---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/add-history?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-History
ms.openlocfilehash: d2c0abb0e6742de3e316fe964d5945375591ef4d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603334"
---
# Add-History

## SINOPSE
Acrescenta as entradas ao histórico de sessão.

## SYNTAX

```
Add-History [[-InputObject] <PSObject[]>] [-Passthru] [<CommonParameters>]
```

## DESCRIPTION

O `Add-History` cmdlet adiciona entradas ao final do histórico da sessão, ou seja, a lista de comandos inseridos durante a sessão atual.

O histórico da sessão é uma lista dos comandos inseridos durante a sessão. O histórico da sessão representa a ordem de execução, o status e os horários de início e término do comando. À medida que você insere cada comando, o PowerShell o adiciona ao histórico para que você possa reutilizá-lo. Para obter mais informações sobre o histórico de sessão, consulte [about_History](About/about_History.md).

O histórico de sessão é gerenciado separadamente do histórico mantido pelo módulo **PSReadLine** .
Ambos os históricos estão disponíveis em sessões em que **PSReadLine** é carregado. Esse cmdlet funciona apenas com o histórico de sessão. Para obter mais informações, consulte [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).

Você pode usar o `Get-History` cmdlet para obter os comandos e passá-los para o `Add-History` , ou pode exportar os comandos para um arquivo CSV ou XML, depois importar os comandos e passar o arquivo importado para o `Add-History` . Você pode usar este cmdlet para adicionar comandos específicos ao histórico ou para criar um arquivo de histórico único que inclui comandos de mais de uma sessão.

## EXEMPLOS

### Exemplo 1: adicionar comandos ao histórico de uma sessão diferente

Este exemplo adiciona os comandos digitados em uma sessão do PowerShell ao histórico de uma sessão diferente do PowerShell.

```powershell
Get-History | Export-Csv c:\testing\history.csv -IncludeTypeInformation
Import-Csv c:\testing\history.csv | Add-History
```

O primeiro comando obtém os objetos que representam os comandos no histórico e exporta-os para o `History.csv` arquivo.

O segundo comando é digitado na linha de comando de uma sessão diferente. Ele usa o `Import-Csv` cmdlet para importar os objetos no `History.csv` arquivo. O operador de pipeline ( `|` ) passa os objetos para o `Add-History` cmdlet, que adiciona os objetos que representam os comandos do `History.csv` arquivo ao histórico de sessão atual.

### Exemplo 2: importar e executar comandos

Este exemplo importa comandos do `History.xml` arquivo, adiciona-os ao histórico de sessão atual e, em seguida, executa os comandos no histórico combinado.

```powershell
Import-Clixml c:\temp\history.xml | Add-History -PassThru | ForEach-Object -Process {Invoke-History}
```

O primeiro comando usa o `Import-Clixml` cmdlet para importar um histórico de comandos que foi exportado para o `History.xml` arquivo. O operador de pipeline passa os comandos para o `Add-History` cmdlet, que adiciona os comandos ao histórico de sessão atual. O parâmetro **PassThru** passa os objetos que representam os comandos adicionados por meio do pipeline.

O comando usa o `ForEach-Object` cmdlet para aplicar o `Invoke-History` comando a cada um dos comandos no histórico combinado. O `Invoke-History` comando é formatado como um bloco de script, entre chaves ( `{}` ), conforme exigido pelo parâmetro **process** do `ForEach-Object` cmdlet.

### Exemplo 3: adicionar comandos no histórico ao final do histórico

Este exemplo adiciona os primeiros cinco comandos no histórico ao final da lista de histórico.

```powershell
Get-History -Id 5 -Count 5 | Add-History
```

O `Get-History` cmdlet obtém os cinco comandos que terminam no comando 5. O operador de pipeline transmite-os para o `Add-History` cmdlet, que os anexa ao histórico atual. O `Add-History` comando não inclui nenhum parâmetro, mas o PowerShell associa os objetos passados pelo pipeline com o parâmetro **InputObject** de `Add-History` .

### Exemplo 4: adicionar comandos em um arquivo. csv ao histórico atual

Este exemplo adiciona os comandos no `History.csv` arquivo ao histórico de sessão atual.

```powershell
$a = Import-Csv c:\testing\history.csv
Add-History -InputObject $a -PassThru
```

O `Import-Csv` cmdlet importa os comandos no `History.csv` arquivo e armazena seu conteúdo na variável `$a` .

O segundo comando usa o `Add-History` cmdlet para adicionar os comandos do `History.csv` ao histórico de sessão atual. Ele usa o parâmetro **InputObject** para especificar a `$a` variável e o parâmetro **PassThru** para gerar um objeto a ser exibido na linha de comando. Sem o parâmetro **PassThru** , o `Add-History` cmdlet não gera nenhuma saída.

### Exemplo 5: adicionar comandos em um arquivo. xml ao histórico atual

Este exemplo adiciona os comandos no `history.xml` arquivo ao histórico de sessão atual.

```powershell
Add-History -InputObject (Import-Clixml c:\temp\history.xml)
```

O parâmetro **InputObject** passa os resultados do comando entre parênteses e o `Add-History` cmdlet. O comando entre parênteses, que é executado primeiro, importa o `history.xml` arquivo para o PowerShell. O `Add-History` cmdlet, em seguida, adiciona os comandos no arquivo ao histórico da sessão.

## PARAMETERS

### -InputObject

Especifica uma matriz de entradas a serem adicionadas ao histórico como objeto **HistoryInfo** ao histórico da sessão.
Você pode usar esse parâmetro para enviar um objeto **HistoryInfo** , como aqueles que são retornados pelos `Get-History` `Import-Clixml` cmdlets,, ou `Import-Csv` , para `Add-History` .

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru

Indica que esse cmdlet retorna um objeto **HistoryInfo** para cada entrada de histórico. Por padrão, este cmdlet não gera saída.

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

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Microsoft. PowerShell. Commands. HistoryInfo

É possível canalizar um objeto **HistoryInfo** para esse cmdlet.

## SAÍDAS

### Nenhum ou Microsoft. PowerShell. Commands. HistoryInfo

Esse cmdlet retornará um objeto **HistoryInfo** se você especificar o parâmetro **PassThru** . Caso contrário, este cmdlet não gera nenhuma saída.

## OBSERVAÇÕES

O histórico de sessão é uma lista dos comandos inseridos durante a sessão junto com a ID. O histórico da sessão representa a ordem de execução, o status e os horários de início e término do comando. À medida que você insere cada comando, o PowerShell o adiciona ao histórico para que você possa reutilizá-lo. Para obter mais informações sobre o histórico de sessão, consulte [about_History](About/about_History.md).

Para especificar os comandos para adicionar ao histórico, use o parâmetro **InputObject**. O `Add-History` comando aceita somente objetos **HistoryInfo** , como aqueles retornados para cada comando pelo `Get-History` cmdlet. Você não pode passar um caminho e nome de arquivo ou uma lista de comandos.

Você pode usar o parâmetro **InputObject** para passar um arquivo de objetos **HistoryInfo** para `Add-History` . Para fazer isso, exporte os resultados de um `Get-History` comando para um arquivo usando o `Export-Csv` `Export-Clixml` cmdlet ou e, em seguida, importe o arquivo usando os `Import-Csv` `Import-Clixml` cmdlets ou. Em seguida, você pode passar o arquivo de objetos **HistoryInfo** importados para `Add-History` por meio de um pipeline ou em uma variável. Para obter mais informações, consulte os exemplos.

O arquivo de objetos **HistoryInfo** que você passa para o `Add-History` cmdlet deve incluir as informações de tipo, títulos de coluna e todas as propriedades dos objetos **HistoryInfo** . Se você pretende passar os objetos de volta para o `Add-History` , não use o parâmetro **NoTypeInformation** do `Export-Csv` cmdlet e não exclua as informações de tipo, os cabeçalhos de coluna ou quaisquer campos no arquivo.

Para modificar o histórico da sessão, exporte a sessão para um arquivo CSV ou XML, modifique o arquivo, importe o arquivo e use `Add-History` -o para acrescentá-lo ao histórico da sessão atual.

## LINKS RELACIONADOS

[Clear-History](Clear-History.md)

[Get-History](Get-History.md)

[Invoke-History](Invoke-History.md)

[about_PSReadLine](../PSReadLine/About/about_PSReadLine.md)

[Get-PSReadLineOption](/powershell/module/psreadline/get-psreadlineoption)

[Set-PSReadLineOption](/powershell/module/psreadline/set-psreadlineoption)

