---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/clear-history?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-History
ms.openlocfilehash: 2288b3a7f7db33dbf22cc47fe2bb16106ea9bb90
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93193019"
---
# Clear-History

## SINOPSE
Exclui entradas do histórico de comandos de sessão do PowerShell.

## SYNTAX

### IDParameter (padrão)

```
Clear-History [[-Id] <int[]>] [[-Count] <int>] [-Newest] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CommandLineParameter

```
Clear-History [[-Count] <int>] [-CommandLine <string[]>] [-Newest] [-WhatIf] [-Confirm]
[<CommonParameters>]
```

## DESCRIPTION

`Clear-History` exclui o histórico de comandos de uma sessão do PowerShell. Cada sessão do PowerShell tem seu próprio histórico de comandos. Para exibir o histórico de comandos, use o `Get-History` cmdlet.

Por padrão, `Clear-History` exclui o histórico de comandos inteiro de uma sessão do PowerShell. Você pode usar parâmetros com `Clear-History` para excluir os comandos selecionados.

`Clear-History` não limpa o `PSReadLine` arquivo de histórico de comandos. O `PSReadLine` módulo armazena um arquivo de histórico que contém cada comando do PowerShell de cada sessão do PowerShell. Em um prompt do PowerShell, use as setas para cima e para baixo no teclado para percorrer o histórico de comandos. Para exibir a `PSReadLine` configuração para o histórico de comandos, use `Get-PSReadLineOption` .
`PSReadLine` fornecido com o PowerShell 5,0 e superior. Para obter mais informações, consulte [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).

## EXEMPLOS

### Exemplo 1: excluir o histórico de comandos de uma sessão do PowerShell

Esse comando exclui todos os comandos do histórico de uma sessão do PowerShell.

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location .\Test
   2 Update-Help
   3 Set-Location C:\Test\Logs
   4 Get-Location
```

```powershell
Clear-History
Get-History
```

```Output
  Id CommandLine
  -- -----------
   5 Clear-History
```

O `Get-History` cmdlet exibe o histórico da sessão do PowerShell. `Clear-History` exclui o histórico de comandos inteiro. `Get-History` exibe o histórico de comandos atualizados e confirma que o histórico anterior foi excluído.

### Exemplo 2: excluir os comandos mais recentes

Esse comando usa os parâmetros **Count** e **mais recentes** para excluir os comandos mais recentes do histórico de uma sessão do PowerShell.

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   3 Get-Command Clear-History -Syntax
   4 Get-Command Clear-History -ShowCommandInfo
   5 Get-Help Get-Alias
   6 Get-Command Get-ChildItem -Syntax
   7 Get-Help Clear-History
   8 Set-Location C:\Test\Logs
   9 Get-Help Get-Variable
  10 Get-Help Get-ChildItem
```

```powershell
Clear-History -Count 5 -Newest
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   3 Get-Command Clear-History -Syntax
   4 Get-Command Clear-History -ShowCommandInfo
   5 Get-Help Get-Alias
  11 Clear-History -Count 5 -Newest
```

O `Get-History` cmdlet exibe o histórico da sessão do PowerShell. `Clear-History` é usado para excluir o histórico de comandos. O parâmetro **Count** especifica o número de comandos a serem excluídos, inclusive a **ID** especificada. O parâmetro **mais recente** especifica que os comandos mais recentes são removidos do histórico. `Get-History`exibe o histórico de comandos atualizados e confirma que os cinco comandos mais recentes foram excluídos, ID **6** ID  -  **10** .

### Exemplo 3: excluir comandos que correspondem a critérios específicos

Este comando exclui os comandos que correspondem aos critérios específicos definidos pelo parâmetro **CommandLine** .

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   3 Get-Command Clear-History -Syntax
   4 Get-Command Clear-History -ShowCommandInfo
   5 Get-Help Get-Alias
   6 Get-Command Get-ChildItem -Syntax
   7 Get-Help Clear-History
```

```powershell
Clear-History -CommandLine *Help*, *Syntax
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   4 Get-Command Clear-History -ShowCommandInfo
   8 Clear-History -CommandLine *Help*, *Syntax
```

O `Get-History` cmdlet exibe o histórico da sessão do PowerShell. `Clear-History` exclui o histórico de comandos. O parâmetro **CommandLine** Especifica comandos que contêm **ajuda** ou terminam com **sintaxe** . `Get-History` exibe o histórico de comandos atualizados e confirma que os comandos **ID 3** , **ID 5** , **ID 6** e **ID 7** foram excluídos.

### Exemplo 4: excluir comandos por número de ID

Este comando exclui itens de histórico específicos usando a **ID** . Para excluir vários comandos, envie uma lista separada por vírgulas de números de **ID** .

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-History
   3 Get-Help Get-Alias
   4 Get-Command Clear-History
   5 Get-Command Clear-History -Syntax
   6 Get-Command Clear-History -ShowCommandInfo
```

```powershell
Clear-History -Id 3, 5
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-History
   4 Get-Command Clear-History
   6 Get-Command Clear-History -ShowCommandInfo
   7 Get-History
   8 Clear-History -Id 3, 5
```

O `Get-History` cmdlet exibe o histórico da sessão do PowerShell. `Clear-History` exclui o histórico de comandos. O parâmetro **ID** especifica quais comandos excluir. `Get-History` exibe o histórico de comandos atualizados e confirma que a **ID 3** e a **ID 5** foram excluídas.

### Exemplo 5: excluir comandos por número de ID e contagem

Esse comando usa os parâmetros **ID** e **Count** para excluir o histórico de comandos. Os comandos são excluídos da **ID** especificada na ordem inversa, o mais recente para o mais antigo.

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   3 Get-Command Clear-History -Syntax
   4 Get-Command Clear-History -ShowCommandInfo
   5 Get-Help Get-Alias
   6 Get-Command Get-ChildItem -Syntax
   7 Get-Help Clear-History
   8 Set-Location C:\Test\Logs
   9 Get-Help Get-Variable
  10 Get-Help Get-ChildItem
```

```powershell
Clear-History -Id 7 -Count 5
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   8 Set-Location C:\Test\Logs
   9 Get-Help Get-Variable
  10 Get-Help Get-ChildItem
  11 Clear-History -Id 7 -Count 5
```

O `Get-History` cmdlet exibe o histórico da sessão do PowerShell. `Clear-History` exclui o histórico de comandos. O parâmetro **ID** especifica o início da **ID 7** . O parâmetro **Count** especifica a exclusão de cinco comandos, inclusive da **ID** especificada. `Get-History`exibe o histórico de comandos atualizados e confirma que cinco comandos foram excluídos, **ID 3** ID  -  **7** .

## PARAMETERS

### -Linha de comando

Exclui o histórico de comandos de uma sessão do PowerShell. A cadeia de caracteres deve ser uma correspondência exata ou usar curingas para corresponder comandos no histórico de sessão do PowerShell exibido pelo `Get-History` . Se você inserir mais de uma cadeia de caracteres, o `Clear-History` excluirá os comandos que correspondem a qualquer uma das cadeias. O parâmetro **CommandLine** pode ser usado com **Count** .

Para cadeias de caracteres com um espaço, use aspas simples. Para obter mais informações, consulte [about_Quoting_Rules](About/about_Quoting_Rules.md).

```yaml
Type: System.String[]
Parameter Sets: CommandLineParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Contagem

Especifica o número de entradas de histórico que o `Clear-History` exclui. Os comandos são excluídos na ordem, começando com a entrada mais antiga no histórico.

Os parâmetros **Count** e **ID** podem ser usados juntos. O parâmetro **Count** especifica o número de comandos a serem excluídos, inclusive a **ID** especificada. A partir da **ID** especificada, os comandos são excluídos na ordem sequencial inversa. Por exemplo, se a **ID** for 30 e a **contagem** for 10, o `Clear-History` excluirá os itens 21 a 30.

Os parâmetros **Count** e **CommandLine** podem ser usados juntos. **Count** especifica o número de comandos a serem excluídos que correspondem ao valor do parâmetro **CommandLine** . Os comandos são excluídos em ordem sequencial.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Especifica a **ID** do histórico de comandos que o `Clear-History` exclui. Para exibir números de **ID** , use o `Get-History` cmdlet. Os números de **ID** são sequenciais e os comandos mantêm seu número de **ID** em uma sessão do PowerShell. O parâmetro **ID** pode ser usado com **Count** e **mais recente** .

```yaml
Type: System.Int32[]
Parameter Sets: IDParameter
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mais recente

Quando o parâmetro **mais recente** for usado, `Clear-History` o excluirá as entradas mais recentes no histórico. Por padrão, `Clear-History` o exclui as entradas mais antigas no histórico.

O parâmetro **mais recente** pode ser usado com **ID** e **contagem** . O parâmetro **Count** especifica o número de comandos a serem excluídos, inclusive a **ID** especificada. A partir da **ID** especificada, os comandos são excluídos em ordem sequencial. Por exemplo, se a **ID** for 30 e a **contagem** for 10, o `Clear-History` excluirá os itens 30 a 39.

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

### -Confirm

Solicita a confirmação antes de executar o `Clear-History` cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Mostra o que aconteceria se o `Clear-History` cmdlet fosse executado. O cmdlet não é executado.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## ENTRADAS

### Nenhum

Não é possível canalizar objetos para `Clear-History` .

## SAÍDAS

### Nenhum

`Clear-History` não gera nenhuma saída.

## OBSERVAÇÕES

O histórico de sessões do PowerShell é uma lista dos comandos inseridos durante uma sessão do PowerShell. Você pode exibir o histórico, adicionar comandos de exclusão e executar comandos por meio do histórico. Para obter mais informações, consulte [about_History](About/about_History.md).

O histórico de sessão é gerenciado separadamente do histórico mantido pelo módulo **PSReadLine** .
Ambos os históricos estão disponíveis em sessões em que **PSReadLine** é carregado. Esse cmdlet funciona apenas com o histórico de sessão. Para obter mais informações, consulte [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).

## LINKS RELACIONADOS

[about_History](About/about_History.md)

[about_PSReadLine](../PSReadLine/About/about_PSReadLine.md)

[about_Quoting_Rules](About/about_Quoting_Rules.md)

[Add-History](Add-History.md)

[Get-History](Get-History.md)

[Invoke-History](Invoke-History.md)

[Get-PSReadLineOption](/powershell/module/psreadline/get-psreadlineoption)

[Set-PSReadLineOption](/powershell/module/psreadline/set-psreadlineoption)
