---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-gridview?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-GridView
ms.openlocfilehash: 473571aa73d9b9331545b80cb5949e7a83c26eff
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193762"
---
# Out-GridView

## SINOPSE
Envia a saída para uma tabela interativa em uma janela separada.

## SYNTAX

### PassThru (padrão)

```
Out-GridView [-InputObject <PSObject>] [-Title <String>] [-PassThru] [<CommonParameters>]
```

### Aguarde

```
Out-GridView [-InputObject <PSObject>] [-Title <String>] [-Wait] [<CommonParameters>]
```

### OutputMode

```
Out-GridView [-InputObject <PSObject>] [-Title <String>] [-OutputMode <OutputModeOption>]
 [<CommonParameters>]
```

## DESCRIPTION

O `Out-GridView` cmdlet envia a saída de um comando para uma janela de exibição de grade em que a saída é exibida em uma tabela interativa.

Como esse cmdlet requer uma interface do usuário, ele não funciona no Windows Server Core ou no Windows nano Server.

Você pode usar os recursos da tabela a seguir para examinar os seus dados:

- Ocultar, mostrar e reordenar colunas
- Classificar linhas
- Filtro Rápido
- Adicionar filtro de critérios
- Copiar e colar

Para obter instruções completas, consulte a seção [observações](#notes) deste artigo.

## EXEMPLOS

### Exemplo 1: processos de saída para um modo de exibição de grade

Este exemplo obtém os processos em execução no computador local e os envia para uma janela de exibição em grade.

```powershell
Get-Process | Out-GridView
```

### Exemplo 2: usar uma variável para processos de saída para um modo de exibição de grade

Este exemplo também obtém os processos em execução no computador local e os envia para uma janela de exibição em grade.

```powershell
$P = Get-Process
$P | Out-GridView
```

A saída do `Get-Process` cmdlet é salva na `$P` variável. Em seguida, `$P` é canalizado para `Out-GridView` .

### Exemplo 3: exibir as propriedades selecionadas em um modo de exibição de grade

Este exemplo exibe as propriedades selecionadas dos processos em execução em um modo de exibição de grade.

```powershell
Get-Process | Select-Object -Property Name, WorkingSet, PeakWorkingSet |
  Sort-Object -Property WorkingSet -Descending | Out-GridView
```

A saída de `Get-Process` é canalizada para `Select-Object` para selecionar as propriedades **Name** , **WorkingSet** e **PeakWorkingSet** . Outro operador de pipeline envia os objetos filtrados para o `Sort-Object` cmdlet para classificá-los em ordem decrescente pelo valor da propriedade **WorkingSet** .
Em seguida, os resultados classificados são canalizados para `Out-GridView` . Agora você pode usar os recursos de exibição em grade para pesquisar, classificar e filtrar os dados.

### Exemplo 4: salvar a saída em uma variável e, em seguida, gerar uma exibição de grade

Esse exemplo salva a saída do cmdlet em uma variável e a envia para `Out-GridView` .

```powershell
($A = Get-ChildItem -Path $PSHOME -Recurse) | Out-GridView
```

`Get-ChildItem` Obtém todos os arquivos no diretório de instalação do PowerShell e seus subdiretórios usando a `$PSHOME` variável automática. Os parênteses no comando estabelecem a ordem das operações. Como resultado, a saída do `Get-ChildItem` comando é salva na `$A` variável antes de ser enviada para `Out-GridView` .

### Exemplo 5: processos de saída para um computador especificado para um modo de exibição de grade

Este exemplo exibe os processos que estão em execução no computador Server01 em uma janela de exibição em grade.

```powershell
Get-Process -ComputerName "Server01" | ogv -Title "Processes - Server01"
```

O examle usa `ogv` , que é o alias para o `Out-GridView` cmdlet. O parâmetro **title** especifica o título da janela.

### Exemplo 6: dados de saída de computadores remotos para um modo de exibição de grade

Este exemplo mostra como enviar dados coletados de computadores remotos para o `Out-GridView` .

```powershell
Invoke-Command -ComputerName S1, S2, S3 -ScriptBlock {Get-Culture} | Out-GridView
```

`Invoke-Command` é executado `Get-Culture` em três computadores remotos. Os dados resultantes são canalizados para `Out-GridView` . Observe que o bloco de script executado no computador remoto não inclui o `Out-GridView` comando. Se incluísse, o comando falharia ao tentar abrir uma janela de exibição em grade em cada um dos computadores remotos.

### Exemplo 7: passar vários itens por meio de `Out-GridView`

Este exemplo permite que você selecione vários processos na `Out-GridView` janela. Os processos selecionados são passados para o `Export-Csv` comando e gravados no `ProcessLog.csv` arquivo.

```powershell
Get-Process | Out-GridView -PassThru | Export-Csv -Path .\ProcessLog.csv
```

O parâmetro **PassThru** de `Out-GridView` permite que você envie vários itens por meio do pipeline. O parâmetro **PassThru** é equivalente a usar o valor **Multiple** do parâmetro **OutputMode** .

### Exemplo 8: criar um atalho do Windows para `Out-GridView`

Este exemplo mostra como usar o parâmetro **Wait** do `Out-GridView` para criar um atalho do Windows para a `Out-GridView` janela.

```powershell
pwsh -Command "Get-Service | Out-GridView -Wait"
```

Essa linha de comando pode ser usada em um atalho do Windows. Sem o parâmetro **Wait** , o PowerShell será encerrado assim que a `Out-GridView` janela fosse aberta, o que fecharia a `Out-GridView` janela quase imediatamente.

## PARAMETERS

### -InputObject

Especifica o objeto que o cmdlet aceita como entrada para `Out-GridView` .

Quando você usa o parâmetro **InputObject** para enviar uma coleção de objetos ao `Out-GridView` , `Out-GridView` o trata a coleção como um objeto de coleção e exibe uma linha que representa a coleção. Para exibir cada objeto na coleção, use um operador de pipeline (|) para enviar objetos para o `Out-GridView` .

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

### -OutputType

Especifica os itens que a janela interativa envia ao pipeline como entrada para outros comandos.
Por padrão, este cmdlet não gera saída. Para enviar itens da janela interativa pelo pipeline, clique para selecionar os itens e, em seguida, clique em OK.

Os valores desse parâmetro determinam quantos itens você pode enviar pelo pipeline.

- nenhuma.  Nenhum item. Este é o valor padrão.
- Única. Zero itens ou um item. Use esse valor quando o próximo comando puder levar apenas um objeto de entrada.
- Vários. Zero, um ou muitos itens. Use esse valor quando o próximo comando puder levar vários objetos de entrada. Esse valor é equivalente ao parâmetro **Passthru** .

Este parâmetro foi introduzido no Windows PowerShell 3.0.

```yaml
Type: Microsoft.PowerShell.Commands.OutputModeOption
Parameter Sets: OutputMode
Aliases:
Accepted values: None, Single, Multiple

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Indica que o cmdlet envia itens da janela interativa para baixo no pipeline como entrada para outros comandos. Por padrão, este cmdlet não gera saída. Este parâmetro é equivalente a usar o valor **Multiple** do parâmetro **OutputMode** .

Para enviar itens da janela interativa pelo pipeline, clique para selecionar os itens e, em seguida, clique em OK. Shift+clique e Ctrl+clique são suportados.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PassThru
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Title

Especifica o texto que aparece na barra de título da `Out-GridView` janela. Por padrão, a barra de título exibe o comando que invoca `Out-GridView` .

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

### -Wait

Indica que o cmdlet suprime o prompt de comando e impede que o Windows PowerShell seja fechado até que a `Out-GridView` janela seja fechada. Por padrão, o prompt de comando retorna quando a `Out-GridView` janela é aberta.

Esse recurso permite que você use os `Out-GridView` cmdlets em atalhos do Windows. Quando `Out-GridView` é usado em um atalho sem o parâmetro **Wait** , a `Out-GridView` janela aparece apenas momentaneamente antes de o PowerShell fechar.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Wait
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

Você pode enviar qualquer objeto para este cmdlet.

## SAÍDAS

### Nenhum

Normalmente, `Out-GridView` o não retorna nenhum objeto. Ao usar o parâmetro **PassThru** , os objetos que representam as linhas selecionadas são retornados para o pipeline.

## OBSERVAÇÕES

Você não pode usar um comando remoto para abrir uma janela de exibição em grade em outro computador.

A saída do comando que você envia para `Out-GridView` não pode ser formatada usando os `Format` cmdlets, como `Format-Table` ou `Format-Wide` cmdlets. Para selecionar propriedades, use o `Select-Object` cmdlet.

Resultado desserializado de comandos remotos podem não ser formatados corretamente na janela de exibição em grade.

**Atalhos de teclado para**`Out-GridView`

|              Use esta tecla:              |                                   Para executar esta ação:                                    |
| --------------------------------------- | -------------------------------------------------------------------------------------------- |
| <kbd>Guia</kbd>                          | Move o cursor da caixa de **filtro** para o menu **Adicionar critérios** para a tabela e de volta. |
| <kbd>Upseta</kbd>                      | Mover uma linha para cima. Move para cabeçalhos de coluna da primeira linha de dados.                             |
| <kbd>Seta</kbd>                    | Mover uma linha para baixo.                                                                           |
| <kbd>LeftArrow</kbd>                    | Na linha de cabeçalho da coluna, mova uma coluna para a esquerda.                                                  |
| <kbd>RightArrow</kbd>                   | Na linha de cabeçalho da coluna, mova uma coluna para a direita.                                                 |
| <kbd>ContextMenuKey</kbd>               | Na linha de cabeçalho da coluna, exibe a opção Selecionar colunas.                                    |
| <kbd>Inserir</kbd> ou <kbd>barra de espaços</kbd> | Na linha de cabeçalho da coluna, classifique os dados da coluna (alterne para A-Z, Z-A).                                    |

**Como usar os recursos da janela de exibição em grade**

**Para ocultar ou mostrar uma coluna:**

1. Clique com o botão direito do mouse em qualquer cabeçalho de coluna e clique em **selecionar colunas** .
2. Na caixa de diálogo **selecionar colunas** , use as teclas de direção para mover as colunas entre as colunas selecionadas para as caixas colunas disponíveis. Somente as colunas na caixa **selecionar colunas** aparecem na janela de exibição em grade.

**Para reordenar colunas:**

Você pode arrastar e soltar colunas no local desejado. Ou use as seguintes etapas:

1. Clique com o botão direito do mouse em qualquer cabeçalho de coluna e clique em **selecionar colunas** .
2. Na caixa de diálogo **selecionar colunas** , use os botões **mover para cima** e mover para **baixo** para reordenar as colunas. As colunas na parte superior da lista aparecem à esquerda das colunas na parte inferior da lista na janela de exibição em grade.

**Como classificar dados de tabela**

- Para classificar os dados, clique em um cabeçalho de coluna.
- Para alterar a ordem de classificação, clique no cabeçalho da coluna novamente. Cada vez que você clicar no mesmo cabeçalho, a ordem de classificação alterna entre crescente para decrescente. O pedido atual é indicado por um triângulo no cabeçalho da coluna.

**Como selecionar dados da tabela**

- Para selecionar uma linha, selecione a linha ou use a seta para cima ou para baixo para navegar até a linha.
- Para selecionar todas as linhas (exceto para a linha de cabeçalho), pressione <kbd>Ctrl</kbd> + <kbd>A</kbd>.
- Para selecionar linhas consecutivas, pressione e segure a tecla <kbd>Shift</kbd> enquanto clica nas linhas ou usando as teclas de direção.
- Para selecionar linhas não consecutivas, pressione a tecla <kbd>Ctrl</kbd> e clique para adicionar uma linha à seleção.
- Não é possível selecionar colunas e nem a linha inteira de cabeçalhos de coluna.

**Como copiar linhas**

- Para copiar uma ou mais linhas da tabela, selecione as linhas e pressione CTRL + C.

  Você pode colar os dados em qualquer programa de texto ou planilha. Não é possível copiar colunas ou partes de linhas e nem a linha de cabeçalhos de coluna.

**Como Pesquisar na tabela (filtro rápido)**

Use a caixa de filtro para pesquisar dados na tabela. Quando você digita na caixa, somente os itens que incluem o texto digitado são exibidos na tabela.

- Pesquise por texto. Para Pesquisar texto na tabela, na caixa filtro, digite o texto a ser localizado.
- Pesquise por várias palavras. Para pesquisar várias palavras na tabela, digite as palavras separadas por espaços. `Out-GridView` exibe as linhas que incluem todas as palavras (AND lógico).
- Procure frases literais. Para pesquisar frases que incluam espaços ou caracteres especiais, coloque a frase entre aspas. `Out-GridView` exibe as linhas que incluem uma correspondência exata para a frase.
- Pesquisar em colunas. Para pesquisar texto em uma ou mais colunas, use o seguinte formato:

  `<column>:<text> [<column>:<text>] ...`

  Por exemplo, para localizar "net" na coluna **DisplayName** , na caixa **filtro** , digite:

  `displayname:net`

  Para localizar linhas com "net" nas colunas **DisplayName** e **Name** , na caixa **filtro** , digite:

  `displayname:net name:net`

- Desative a pesquisa. Para exibir a tabela inteira novamente, clique no botão X vermelho no canto superior direito da caixa de **filtro** ou exclua o texto da caixa de **filtro** .

**Use critérios para filtrar a tabela**

Você pode usar regras ou critérios para determinar quais itens são exibidos na tabela. Os itens aparecem apenas quando atendem a todos os critérios que você estabelece. Os critérios disponíveis são determinados pelas propriedades dos objetos exibidos na janela de exibição em grade e tipos do .NET Framework dessas propriedades.

Cada critério tem o seguinte formato:

`<column> <operator> <value>`

Os critérios para propriedades diferentes são conectados por **e** . Os critérios para a mesma propriedade são conectados por **ou** . Você não pode alterar os conectores lógicos.

Os critérios afetam somente a exibição. Ele não exclui itens da tabela.

**Como adicionar critérios**

1. Para exibir o botão de menu **Adicionar critérios** , no canto superior direito da janela, clique na seta de expansão.
2. Clique no botão de menu **Adicionar critérios** .
3. Clique para selecionar colunas (propriedades). Você pode selecionar uma ou mais propriedades.
4. Quando terminar de selecionar propriedades, clique no botão **Adicionar** .
5. Para cancelar as adições, clique em **Cancelar** .
6. Para adicionar mais critérios, clique no botão **Adicionar critérios** novamente.

**Como editar um critério**

- Para alterar um operador, clique no valor do operador azul e, em seguida, selecione um operador diferente na lista suspensa.
- Para inserir ou alterar um valor, digite um valor na caixa valor. Se você inserir um valor que não é válido, um ícone de X circular aparece. Para removê-lo, altere o valor.
- Para criar uma instrução **ou** , adicione um critério com a mesma propriedade.

**Como excluir critérios**

- Para excluir os critérios selecionados, clique no X vermelho ao lado de cada critério.
- Para excluir todos os critérios, clique no botão **limpar tudo** .

## LINKS RELACIONADOS

[Out-File](Out-File.md)

[Out-Printer](Out-Printer.md)

[Out-String](Out-String.md)
