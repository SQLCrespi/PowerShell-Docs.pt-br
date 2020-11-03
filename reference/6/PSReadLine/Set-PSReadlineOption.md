---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: PSReadLine
ms.date: 06/30/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/set-psreadlineoption?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSReadLineOption
ms.openlocfilehash: d3e3ee1dcde36ac09f8441aff7ce48797cf48b5f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93194040"
---
# Set-PSReadLineOption

## Sinopse
Personaliza o comportamento da edição de linha de comando no **PSReadLine** .

## Sintaxe

```
Set-PSReadLineOption [-EditMode <EditMode>] [-ContinuationPrompt <String>] [-HistoryNoDuplicates]
 [-AddToHistoryHandler <System.Func[System.String,System.Object]>]
 [-CommandValidationHandler <System.Action[System.Management.Automation.Language.CommandAst]>]
 [-HistorySearchCursorMovesToEnd] [-MaximumHistoryCount <Int32>] [-MaximumKillRingCount <Int32>]
 [-ShowToolTips] [-ExtraPromptLineCount <Int32>] [-DingTone <Int32>] [-DingDuration <Int32>]
 [-BellStyle <BellStyle>] [-CompletionQueryItems <Int32>] [-WordDelimiters <String>]
 [-HistorySearchCaseSensitive] [-HistorySaveStyle <HistorySaveStyle>] [-HistorySavePath <String>]
 [-AnsiEscapeTimeout <Int32>] [-PromptText <String[]>] [-ViModeIndicator <ViModeStyle>]
 [-ViModeChangeHandler <ScriptBlock>] [-Colors <Hashtable>] [<CommonParameters>]
```

## Descrição

O `Set-PSReadLineOption` cmdlet personaliza o comportamento do módulo **PSReadLine** quando você está editando a linha de comando. Para exibir as configurações de **PSReadLine** , use `Get-PSReadLineOption` .

## Exemplos

### Exemplo 1: definir cores de primeiro e segundo plano

Este exemplo define **PSReadLine** para exibir o token de **Comentário** com texto em primeiro plano verde em um plano de fundo cinza. Na sequência de escape usada no exemplo, **32** representa a cor do primeiro plano e **47** representa a cor do plano de fundo.

```powershell
Set-PSReadLineOption -Colors @{ "Comment"="`e[32;47m" }
```

Você pode optar por definir apenas uma cor de texto em primeiro plano. Por exemplo, uma cor de texto de primeiro plano verde brilhante para o token de **Comentário** : ``"Comment"="`e[92m"`` .

### Exemplo 2: definir estilo de sino

Neste exemplo, o **PSReadLine** responderá a erros ou condições que exigem a atenção do usuário.
O **bellstyle** é definido para emitir um aviso sonoro em 1221 Hz para 60 ms.

```powershell
Set-PSReadLineOption -BellStyle Audible -DingTone 1221 -DingDuration 60
```

> [!NOTE]
> Esse recurso pode não funcionar em todos os hosts em plataformas.

### Exemplo 3: definir várias opções

`Set-PSReadLineOption` pode definir várias opções com uma tabela de hash.

```powershell
$PSReadLineOptions = @{
    EditMode = "Emacs"
    HistoryNoDuplicates = $true
    HistorySearchCursorMovesToEnd = $true
    Colors = @{
        "Command" = "#8181f7"
    }
}
Set-PSReadLineOption @PSReadLineOptions
```

A `$PSReadLineOptions` tabela de hash define as chaves e os valores. `Set-PSReadLineOption` usa as chaves e valores com `@PSReadLineOptions` para atualizar as opções de **PSReadLine** .

Você pode exibir as chaves e os valores que inserem o nome da tabela de hash `$PSReadLineOptions` na linha de comando do PowerShell.

### Exemplo 4: definir opções de várias cores

Este exemplo mostra como definir mais de um valor de cor em um único comando.

```powershell
Set-PSReadLineOption -Colors @{
  Command            = 'Magenta'
  Number             = 'DarkGray'
  Member             = 'DarkGray'
  Operator           = 'DarkGray'
  Type               = 'DarkGray'
  Variable           = 'DarkGreen'
  Parameter          = 'DarkGreen'
  ContinuationPrompt = 'DarkGray'
  Default            = 'DarkGray'
}
```

### Exemplo 5: definir valores de cor para vários tipos

Este exemplo mostra três métodos diferentes para definir a cor dos tokens exibidos em **PSReadLine** .

```powershell
Set-PSReadLineOption -Colors @{
 # Use a ConsoleColor enum
 "Error" = [ConsoleColor]::DarkRed

 # 24 bit color escape sequence
 "String" = "$([char]0x1b)[38;5;100m"

 # RGB value
 "Command" = "#8181f7"
}
```

### Exemplo 6: usar ViModeChangeHandler para exibir as alterações do modo vi

Este exemplo emite uma alteração de cursor de VT escape em resposta a uma alteração no modo **vi** .

```powershell
function OnViModeChange {
    if ($args[0] -eq 'Command') {
        # Set the cursor to a blinking block.
        Write-Host -NoNewLine "`e[1 q"
    } else {
        # Set the cursor to a blinking line.
        Write-Host -NoNewLine "`e[5 q"
    }
}
Set-PSReadLineOption -ViModeIndicator Script -ViModeChangeHandler $Function:OnViModeChange
```

A função **OnViModeChange** define as opções de cursor para os modos **vi** : INSERT e Command.
**ViModeChangeHandler** usa o `Function:` provedor para fazer referência a **OnViModeChange** como um objeto de bloco de script.

Para obter mais informações, consulte [about_Providers](/powershell/module/microsoft.powershell.core/about/about_providers).

## Parâmetros

### -AddToHistoryHandler

Especifica um **scriptblock** que controla quais comandos são adicionados ao histórico de **PSReadLine** .

O **scriptblock** recebe a linha de comando como entrada. Se o **scriptblock** retornar `$True` , a linha de comando será adicionada ao histórico.

```yaml
Type: System.Func`2[System.String,System.Object]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AnsiEscapeTimeout

Essa opção é específica ao Windows quando a entrada é redirecionada, por exemplo, ao ser executada em `tmux` ou `screen` .

Com a entrada redirecionada no Windows, muitas chaves são enviadas como uma sequência de caracteres começando com o caractere de escape. É impossível distinguir entre um único caractere de escape seguido de mais caracteres e uma sequência de escape válida.

A suposição é que o terminal possa enviar os caracteres mais rápido do que os tipos de usuário. **PSReadLine** aguarda esse tempo limite antes de concluir que recebeu uma sequência de escape completa.

Se você vir caracteres aleatórios ou inesperados ao digitar, poderá ajustar esse tempo limite.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### -Bellstyle

Especifica como o **PSReadLine** responde a várias condições ambíguas e de erro.

Os valores válidos são os seguintes:

- **Audível** : um breve bipe.
- **Visual** : o texto pisca brevemente.
- **Nenhum** : nenhum comentário.

```yaml
Type: Microsoft.PowerShell.BellStyle
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Audible
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cores

O parâmetro **Colors** especifica várias cores usadas pelo **PSReadLine** .

O argumento é uma tabela de hash em que as chaves especificam qual elemento e os valores especificam a cor.
Para obter mais informações, consulte [about_Hash_Tables](/powershell/module/microsoft.powershell.core/about/about_hash_tables).

As cores podem ser um valor de **ConsoleColor** , por exemplo `[ConsoleColor]::Red` , ou uma sequência de escape ANSI válida. As sequências de escape válidas dependem do seu terminal. No PowerShell 5,0, uma sequência de escape de exemplo para texto vermelho é `$([char]0x1b)[91m` . No PowerShell 6 e acima, a mesma sequência de escape é `` `e[91m`` . Você pode especificar outras sequências de escape, incluindo os seguintes tipos:

- cor de 256
- cor de 24 bits
- Primeiro plano, plano de fundo ou ambos
- Inverso, negrito

Para obter mais informações sobre códigos de cor ANSI, consulte [código de escape ANSI](https://wikipedia.org/wiki/ANSI_escape_code#Colors_) na Wikipédia.

As chaves válidas incluem:

- **ContinuationPrompt** : a cor do prompt de continuação.
- **Ênfase** : a cor de ênfase. Por exemplo, o texto correspondente ao pesquisar o histórico.
- **Erro** : a cor do erro. Por exemplo, no prompt.
- **Seleção** : a cor para realçar a seleção de menu ou o texto selecionado.
- **Padrão** : a cor padrão do token.
- **Comentário** : a cor do token de comentário.
- **Palavra-chave** : a cor do token de palavra-chave.
- **String** : a cor do token da cadeia de caracteres.
- **Operador** : a cor do token do operador.
- **Variável** : a cor do token variável.
- **Comando** : a cor do token de comando.
- **Parâmetro** : a cor do token do parâmetro.
- **Tipo** : a cor do token de tipo.
- **Número** : a cor do token de número.
- **Membro** : a cor do token do nome do membro.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CommandValidationHandler

Especifica um **scriptblock** que é chamado de **ValidateAndAcceptLine** . Se uma exceção for lançada, a validação falhará e o erro será relatado.

Antes de lançar uma exceção, o manipulador de validação pode colocar o cursor no ponto do erro para facilitar a correção. Um manipulador de validação também pode alterar a linha de comando, como para corrigir erros tipográficos comuns.

**ValidateAndAcceptLine** é usado para evitar a confusão de seu histórico com comandos que não funcionam.

```yaml
Type: System.Action`1[System.Management.Automation.Language.CommandAst]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CompletionQueryItems

Especifica o número máximo de itens de conclusão que são mostrados sem solicitação.

Se o número de itens a serem mostrados for maior que esse valor, **PSReadLine** solicitará **Sim/não** antes de exibir os itens de conclusão.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContinuationPrompt

Especifica a cadeia de caracteres exibida no início das linhas subsequentes quando a entrada de várias linhas é inserida. O padrão é duplo de sinais de maior que ( `>>` ). Uma cadeia de caracteres vazia é válida.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: >>
Accept pipeline input: False
Accept wildcard characters: False
```

### -DingDuration

Especifica a duração do aviso sonoro quando **bellstyle** é definido como **audível** .

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 50ms
Accept pipeline input: False
Accept wildcard characters: False
```

### -DingTone

Especifica o Tom em Hertz (Hz) do bipe quando **bellstyle** é definido como **audível** .

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1221
Accept pipeline input: False
Accept wildcard characters: False
```

### -EditMode

Especifica o modo de edição de linha de comando. O uso desse parâmetro redefine as associações de chave definidas por `Set-PSReadLineKeyHandler` .

Os valores válidos são os seguintes:

- **Windows** : associações de chave emulam o PowerShell, o cmd e o Visual Studio.
- **Emacs** : associações de chave emulam bash ou Emacs.
- **Vi** : associações de chave emulam vi.

Use `Get-PSReadLineKeyHandler` para ver as associações de chave para o **EditMode** configurado no momento.

```yaml
Type: Microsoft.PowerShell.EditMode
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Windows
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExtraPromptLineCount

Especifica o número de linhas extras.

Se o prompt se estender por mais de uma linha, especifique um valor para esse parâmetro. Use esta opção quando desejar que linhas extras estejam disponíveis quando o **PSReadLine** exibir o prompt depois de mostrar alguma saída. Por exemplo, **PSReadLine** retorna uma lista de conclusões.

Essa opção é necessária para menos do que nas versões anteriores do **PSReadLine** , mas é útil quando a `InvokePrompt` função é usada.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -HistoryNoDuplicates

Esta opção controla o comportamento de recuperação. Comandos duplicados ainda são adicionados ao arquivo de histórico.
Quando essa opção é definida, somente a invocação mais recente é exibida durante a rechamada de comandos. Comandos repetidos são adicionados ao histórico para preservar a ordenação durante a RECALL. No entanto, normalmente você não deseja ver o comando várias vezes ao chamar ou pesquisar o histórico.

Por padrão, a propriedade **HistoryNoDuplicates** do objeto **PSConsoleReadLineOptions** global é definida como `True` . O uso desse **SwitchParameter** define o valor da propriedade como `True` . Para alterar o valor da propriedade, você deve especificar o valor do **SwitchParameter** da seguinte maneira: `-HistoryNoDuplicates:$False` .

Usando o comando a seguir, você pode definir o valor da propriedade diretamente:

`(Get-PSReadLineOption).HistoryNoDuplicates = $False`

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

### -HistorySavePath

Especifica o caminho para o arquivo em que o histórico é salvo. Computadores que executam plataformas Windows ou não Windows armazenam o arquivo em locais diferentes. O nome do arquivo é armazenado em uma variável `$($host.Name)_history.txt` , por exemplo `ConsoleHost_history.txt` .

Se você não usar esse parâmetro, o caminho padrão será o seguinte:

**Windows**

`$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine\$($host.Name)_history.txt`

**Não Windows**

`$env:XDG_DATA_HOME/powershell/PSReadLine\$($host.Name)_history.txt`

`$env:HOME/.local/share/powershell/PSReadLine\$($host.Name)_history.txt`

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: A file named $($host.Name)_history.txt in $env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine on Windows and $env:XDG_DATA_HOME/powershell/PSReadLine or $env:HOME/.local/share/powershell/PSReadLine on non-Windows platforms
Accept pipeline input: False
Accept wildcard characters: False
```

### -HistorySaveStyle

Especifica como o **PSReadLine** salva o histórico.

Estes são os valores válidos:

- **SaveIncrementally** : salvar histórico depois que cada comando for executado e compartilhar entre várias instâncias do PowerShell.
- **SaveAtExit** : acrescentar arquivo de histórico quando o PowerShell for encerrado.
- **SaveNothing** : não use um arquivo de histórico.

```yaml
Type: Microsoft.PowerShell.HistorySaveStyle
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: SaveIncrementally
Accept pipeline input: False
Accept wildcard characters: False
```

### -HistorySearchCaseSensitive

Especifica que a pesquisa de histórico diferencia maiúsculas de minúsculas em funções como **ReverseSearchHistory** ou **HistorySearchBackward** .

Por padrão, a propriedade **HistorySearchCaseSensitive** do objeto **PSConsoleReadLineOptions** global é definida como `False` . O uso desse **SwitchParameter** define o valor da propriedade como `True` . Para alterar o valor da propriedade de volta, você deve especificar o valor do **SwitchParameter** da seguinte maneira: `-HistorySearchCaseSensitive:$False` .

Usando o comando a seguir, você pode definir o valor da propriedade diretamente:

`(Get-PSReadLineOption).HistorySearchCaseSensitive = $False`

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

### -HistorySearchCursorMovesToEnd

Indica que o cursor se move para o final dos comandos que você carrega do histórico usando uma pesquisa.
Quando esse parâmetro é definido como `$False` , o cursor permanece na posição em que você pressionou as setas para cima ou para baixo.

Por padrão, a propriedade **HistorySearchCursorMovesToEnd** do objeto **PSConsoleReadLineOptions** global é definida como `False` . Usando este **SwitchParameter** , defina o valor da propriedade como `True` . Para alterar o valor da propriedade de volta, você deve especificar o valor do **SwitchParameter** da seguinte maneira: `-HistorySearchCursorMovesToEnd:$False` .

Usando o comando a seguir, você pode definir o valor da propriedade diretamente:

`(Get-PSReadLineOption).HistorySearchCursorMovesToEnd = $False`

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

### -MaximumHistoryCount

Especifica o número máximo de comandos a serem salvos no histórico de **PSReadLine** .

O histórico de **PSReadLine** é separado do histórico do PowerShell.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumKillRingCount

Especifica o número máximo de itens armazenados no Kill Ring.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 10
Accept pipeline input: False
Accept wildcard characters: False
```

### -PromptText

Quando há um erro de análise, o **PSReadLine** altera uma parte do prompt vermelho. O **PSReadLine** analisa sua função de prompt para determinar como alterar apenas a cor de parte do prompt. Essa análise não é de 100% confiável.

Use esta opção se **PSReadLine** estiver alterando seu prompt de maneiras inesperadas. Inclua qualquer espaço em branco à direita.

Por exemplo, se a função de prompt se parecer com o exemplo a seguir:

`function prompt { Write-Host -NoNewLine -ForegroundColor Yellow "$pwd"; return "# " }`

Em seguida, defina:

`Set-PSReadLineOption -PromptText "# "`

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: >
Accept pipeline input: False
Accept wildcard characters: False
```

### -Dicas de ferramentas

Ao exibir as conclusões possíveis, as dicas de ferramentas são mostradas na lista de conclusões.

Essa opção é habilitada por padrão. Essa opção não foi habilitada por padrão nas versões anteriores do **PSReadLine** . Para desabilitar, defina essa opção como `$False` .

Por padrão, a propriedade **Extooltips** do objeto **PSConsoleReadLineOptions** global é definida como `True` . O uso desse **SwitchParameter** define o valor da propriedade como `True` . Para alterar o valor da propriedade, você deve especificar o valor do **SwitchParameter** da seguinte maneira: `-ShowToolTips:$False` .

Usando o comando a seguir, você pode definir o valor da propriedade diretamente:

`(Get-PSReadLineOption).ShowToolTips = $False`

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -ViModeChangeHandler

Quando o **ViModeIndicator** é definido como `Script` , o bloco de script fornecido será invocado sempre que o modo for alterado. O bloco de script recebe um argumento do tipo `ViMode` .

Esse parâmetro foi introduzido no PowerShell 7.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ViModeIndicator

Essa opção define a indicação visual para o modo **vi** atual. O modo de inserção ou o modo de comando.

Os valores válidos são os seguintes:

- **Nenhum** : não há nenhuma indicação.
- **Prompt** : o prompt muda de cor.
- **Cursor** : o tamanho das alterações do cursor.
- **Script** : o texto especificado pelo usuário é impresso.

```yaml
Type: Microsoft.PowerShell.ViModeStyle
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WordDelimiters

Especifica os caracteres que delimitam palavras para funções como **ForwardWord** ou **KillWord** .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: ;:,.[]{}()/\|^&*-=+'"–—―
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Entradas

### Nenhum

Não é possível canalizar objetos para `Set-PSReadLineOption.`

## Saídas

### Nenhum

Este cmdlet não gera saída.

## Observações

## Links relacionados

[about_PSReadLine](./About/about_PSReadLine.md)

[Get-PSReadLineKeyHandler](Get-PSReadLineKeyHandler.md)

[Get-PSReadLineOption](Get-PSReadLineOption.md)

[Remove-PSReadLineKeyHandler](Remove-PSReadLineKeyHandler.md)

[Set-PSReadLineKeyHandler](Set-PSReadLineKeyHandler.md)
