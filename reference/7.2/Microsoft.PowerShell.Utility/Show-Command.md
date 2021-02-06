---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/29/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/show-command?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-Command
ms.openlocfilehash: 87bdd5a9610267b8fce9e391431d24872a77e2de
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596184"
---
# Show-Command

## SINOPSE
Exibe informações de comando do PowerShell em uma janela gráfica.

## SYNTAX

```
Show-Command [[-Name] <String>] [-Height <Double>] [-Width <Double>] [-NoCommonParameter]
 [-ErrorPopup] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION

O `Show-Command` cmdlet permite criar um comando do PowerShell em uma janela de comando. Você pode usar os recursos da janela de comando para executar o comando ou fazê-la retornar o comando para você.

`Show-Command` é uma ferramenta de ensino e aprendizado muito útil. `Show-Command` funciona em todos os tipos de comando, incluindo cmdlets, funções, fluxos de trabalho e comandos CIM.

Sem parâmetros, `Show-Command` exibe uma janela de comando que lista todos os comandos disponíveis em todos os módulos instalados. Para localizar os comandos em um módulo, selecione o módulo na lista suspensa Modules. Para selecionar um comando, clique no nome do comando.

Para usar a janela de comando, selecione um comando, seja usando o nome ou clicando no nome do comando na lista **comandos** . Cada conjunto de parâmetros é exibido em uma guia separada. Os asteriscos indicam os parâmetros obrigatórios. Para inserir valores para um parâmetro, digite o valor na caixa de texto ou selecione o valor da caixa suspensa. Para adicionar um parâmetro de opção, clique para selecionar a caixa de seleção do parâmetro.

Quando estiver pronto, você pode clicar em **Copy** para copiar o comando que criou para a área de transferência ou clicar em **Run** para executar o comando. Você também pode usar o parâmetro **PassThru** para retornar o comando para o programa host, como o console do PowerShell. Para cancelar a seleção de comando e retornar à exibição que exibe todos os comandos, pressione CTRL e clique no comando selecionado.

No ISE (ambiente de script integrado) do PowerShell, uma variação da `Show-Command` janela é exibida por padrão. Para obter informações sobre como usar essa janela de comando, consulte os tópicos de ajuda do ISE do PowerShell.

Esse cmdlet foi reintroduzido no PowerShell 7.

Como esse cmdlet requer uma interface do usuário, ele não funciona no Windows Server Core ou no Windows nano Server. Esse cmdlet só está disponível em sistemas Windows que dão suporte à área de trabalho do Windows.

## EXEMPLOS

### Exemplo 1: abrir a janela de comandos

Este exemplo exibe a exibição padrão da `Show-Command` janela. A janela **comandos** exibe uma lista de todos os comandos em todos os módulos que estão instalados no computador.

```powershell
Show-Command
```

### Exemplo 2: abrir um cmdlet na janela de comandos

Este exemplo exibe o `Invoke-Command` cmdlet na janela de **comando** . Você pode usar essa exibição para executar `Invoke-Command` comandos.

```powershell
Show-Command -Name "Invoke-Command"
```

### Exemplo 3: abrir um cmdlet com parâmetros especificados

Esse comando abre uma `Show-Command` janela para o `Connect-PSSession` cmdlet.

```powershell
Show-Command -Name "Connect-PSSession" -Height 700 -Width 1000 -ErrorPopup
```

Os parâmetros de **altura** e **largura** especificam a dimensão da janela de comando. O parâmetro **ErrorPopup** exibe a janela de comando de erro.

Quando você clica em **executar**, o `Connect-PSSession` comando é executado, assim como faria se você tivesse digitado o `Connect-PSSession` comando na linha de comando.

### Exemplo 4: especificar novos valores de parâmetro padrão para um cmdlet

Este exemplo usa a `$PSDefaultParameterValues` variável automática para definir novos valores padrão para os parâmetros de **altura**, **largura** e **ErrorPopup** do `Show-Command` cmdlet.

```powershell
$PSDefaultParameterValues = @{
    "Show-Command:Height" = 700
    "Show-Command:Width" = 1000
    "Show-Command:ErrorPopup" = $True
}
```

Agora, quando você executa um `Show-Command` comando, os novos padrões são aplicados automaticamente. Para usar esses valores padrão em cada sessão do PowerShell, adicione a `$PSDefaultParameterValues` variável ao seu perfil do PowerShell. Para obter mais informações, consulte [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md) e [about_Parameters_Default_Values](../Microsoft.PowerShell.Core/About/about_Parameters_Default_Values.md).

### Exemplo 5: enviar a saída para um modo de exibição de grade

Este comando mostra como usar os `Show-Command` `Out-GridView` cmdlets e juntos.

```powershell
Show-Command Get-ChildItem | Out-GridView
```

O comando usa o `Show-Command` cmdlet para abrir uma janela de comando para o `Get-ChildItem` cmdlet.
Quando você clica no botão **executar** , o `Get-ChildItem` comando é executado e gera a saída. O operador de pipeline (|) envia a saída do `Get-ChildItem` comando para o `Out-GridView` cmdlet, que exibe a `Get-ChildItem` saída em uma janela interativa.

### Exemplo 6: exibir um comando que você cria na janela comandos

Este exemplo mostra o comando que você criou na `Show-Command` janela. O comando usa o parâmetro **PassThru** , que retorna os `Show-Command` resultados em uma cadeia de caracteres.

```powershell
Show-Command -PassThru
```

```Output
Get-EventLog -LogName "Windows PowerShell" -Newest 5
```

Por exemplo, se você usar a `Show-Command` janela para criar um `Get-EventLog` comando que obtém os cinco eventos mais recentes no log de eventos do Windows PowerShell e, em seguida, clicar em **OK**, o comando retornará a saída mostrada acima. A exibição da cadeia de caracteres de comando ajuda você a aprender o PowerShell.

### Exemplo 7: salvar um comando em uma variável

Este exemplo mostra como executar a cadeia de caracteres de comando que você obtém ao usar o parâmetro **PassThru** do `Show-Command` cmdlet. Essa estratégia permite ver o comando e usá-lo.

```powershell
$C = Show-Command -PassThru
$C
Invoke-Expression $C
```

```Output
Get-EventLog -LogName "PowerShell" -Newest 5

Index Time          EntryType   Source                 InstanceID Message
----- ----          ---------   ------                 ---------- -------
11520 Dec 16 16:37  Information Windows PowerShell            400 Engine state is changed from None to Available...
11519 Dec 16 16:37  Information Windows PowerShell            600 Provider "Variable" is Started. ...
11518 Dec 16 16:37  Information Windows PowerShell            600 Provider "Registry" is Started. ...
11517 Dec 16 16:37  Information Windows PowerShell            600 Provider "Function" is Started. ...
11516 Dec 16 16:37  Information Windows PowerShell            600 Provider "FileSystem" is Started. ...
```

O primeiro comando usa o parâmetro **PassThru** do `Show-Command` cmdlet e salva os resultados do comando na `$C` variável. Nesse caso, usamos a `Show-Command` janela para criar um `Get-EventLog` comando que obtém os cinco eventos mais recentes no log de eventos do Windows PowerShell. Quando você clica em **OK**, `Show-Command` retorna a cadeia de caracteres de comando, que é salva na `$C` variável.

### Exemplo 8: salvar a saída de um comando em uma variável

Este exemplo usa o parâmetro **ErrorPopup** para salvar a saída de um comando em uma variável.

```powershell
$P = Show-Command Get-Process -ErrorPopup
$P
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    473      33    94096     112532   709     2.06   4492 powershell
```

Além de exibir erros em uma janela, o **ErrorPopup** retorna a saída do comando para o comando atual, em vez de criar um novo comando. Quando você executar esse comando, a `Show-Command` janela será aberta. Você pode usar os recursos de janela para definir valores de parâmetro. Para executar o comando, clique no botão **executar** na `Show-Command` janela.

## PARAMETERS

### -ErrorPopup

Indica que o cmdlet exibe erros em uma janela pop-up, além de exibi-los na linha de comando. Por padrão, quando um comando executado em uma `Show-Command` janela gera um erro, o erro é exibido somente na linha de comando.

Além disso, quando você executa o comando (usando o botão **executar** na `Show-Command` janela), o parâmetro **ErrorPopup** retorna os resultados do comando para o comando atual, em vez de executar o comando e retornar sua saída para um novo comando. Você pode usar esse recurso para salvar os resultados do comando em uma variável.

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

### -Altura

Especifica a altura da `Show-Command` janela em pixels. Insira um valor entre 300 e o número de pixels na resolução de tela. Se o valor for muito grande para exibir a janela de comando na tela, o `Show-Command` gerará um erro. A altura padrão é 600 pixels. Para um `Show-Command` comando que inclui o parâmetro **Name** , a altura padrão é de 300 pixels.

```yaml
Type: System.Double
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Exibe uma janela de comando para o comando especificado. Insira o nome de um comando, como o nome de um cmdlet, uma função ou um comando CIM. Se você omitir esse parâmetro, `Show-Command` o exibirá uma janela de comando que lista todos os comandos do PowerShell em todos os módulos instalados no computador.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CommandName

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoCommonParameter

Indica que esse cmdlet omite a seção de parâmetros comuns da exibição do comando. Por padrão, Parâmetros Comuns aparece em uma seção expansível na parte inferior da janela de comando.

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

Retorna um objeto que representa o item com que você está trabalhando. Por padrão, este cmdlet não gera saída. Para executar a cadeia de caracteres de comando, copie e cole-a no prompt de comando ou salve-a em uma variável e use o `Invoke-Expression` cmdlet para executar a cadeia de caracteres na variável.

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

### -Largura

Especifica a largura da `Show-Command` janela em pixels. Insira um valor entre 300 e o número de pixels na resolução de tela. Se o valor for muito grande para exibir a janela de comando na tela, o `Show-Command` gerará um erro. A largura padrão é 300 pixels.

```yaml
Type: System.Double
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

### Nenhum

Não é possível canalizar a entrada para `Show-Command` .

## SAÍDAS

### Nenhum, System. String, System. Object

Quando você usa o parâmetro **PassThru** , `Show-Command` retorna uma cadeia de caracteres de comando. Quando você usa o parâmetro **ErrorPopup** , `Show-Command` o retorna a saída do comando (qualquer objeto). Caso contrário, `Show-Command` o não gera nenhuma saída.

## OBSERVAÇÕES

Esse cmdlet só está disponível em plataformas Windows.

`Show-Command` Não funciona em sessões remotas.

## LINKS RELACIONADOS
