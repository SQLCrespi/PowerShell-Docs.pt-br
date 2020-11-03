---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 2/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-alias?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Alias
ms.openlocfilehash: 86eff41bc9784627db82689108d01cbd71840e77
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192797"
---
# Set-Alias

## SINOPSE
Cria ou altera um alias para um cmdlet ou outro comando na sessão atual do PowerShell.

## SYNTAX

### Padrão (padrão)

```
Set-Alias [-Name] <string> [-Value] <string> [-Description <string>] [-Option <ScopedItemOptions>]
 [-PassThru] [-Scope <string>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

O `Set-Alias` cmdlet cria ou altera um alias para um cmdlet ou um comando, como uma função, script, arquivo ou outro executável. Um alias é um nome alternativo que se refere a um cmdlet ou comando.
Por exemplo, `sal` é o alias para o `Set-Alias` cmdlet. Para obter mais informações, consulte [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

Um cmdlet pode ter vários aliases, mas um alias só pode ser associado a um cmdlet. Você pode usar `Set-Alias` para reatribuir um alias existente a outro cmdlet ou alterar as propriedades de um alias, como a descrição.

Um alias que é criado ou alterado pelo `Set-Alias` não é permanente e só está disponível durante a sessão atual do PowerShell. Quando a sessão do PowerShell é fechada, o alias é removido.

## EXEMPLOS

### Exemplo 1: criar um alias para um cmdlet

Este comando cria um alias para um cmdlet na sessão atual do PowerShell.

```
PS> Set-Alias -Name list -Value Get-ChildItem

PS> Get-Alias -Name list

CommandType     Name
-----------     ----
Alias           list -> Get-ChildItem
```

O `Set-Alias` cmdlet cria um alias na sessão atual do PowerShell. O parâmetro **Name** especifica o nome do alias, `list` . O parâmetro **Value** especifica o cmdlet que o alias executa.

Para executar o alias, digite `list` na linha de comando do PowerShell.

### Exemplo 2: Reatribuir um alias existente a um cmdlet diferente

Esse comando reatribui um alias existente para executar um cmdlet diferente.

```
PS> Get-Alias -Name list

CommandType     Name
-----------     ----
Alias           list -> Get-ChildItem

PS> Set-Alias -Name list -Value Get-Location

PS> Get-Alias -Name list

CommandType     Name
-----------     ----
Alias           list -> Get-Location
```

O `Get-Alias` cmdlet usa o parâmetro **Name** para exibir o `list` alias. O `list` alias está associado ao `Get-ChildItem` cmdlet. Quando o `list` alias é executado, os itens no diretório atual são exibidos.

O `Set-Alias` cmdlet usa o parâmetro **Name** para especificar o `list` alias. O parâmetro **Value** associa o alias ao `Get-Location` cmdlet.

O `Get-Alias` cmdlet usa o parâmetro **Name** para exibir o `list` alias. O `list` alias está associado ao `Get-Location` cmdlet. Quando o `list` alias é executado, o local do diretório atual é exibido.

### Exemplo 3: criar e alterar um alias somente leitura

Este comando cria um alias somente leitura. A opção somente leitura impede alterações involuntárias em um alias. Para alterar ou excluir um alias somente leitura, use o parâmetro **Force** .

```
PS> Set-Alias -Name loc -Value Get-Location -Option ReadOnly -PassThru | Format-List -Property *

DisplayName         : loc -> Get-Location
Definition          : Get-Location
Options             : ReadOnly
Description         :
Name                : loc
CommandType         : Alias

PS> Set-Alias -Name loc -Value Get-Location -Option ReadOnly -Description 'Displays the current directory' -Force -PassThru | Format-List -Property *

DisplayName         : loc -> Get-Location
Definition          : Get-Location
Options             : ReadOnly
Description         : Displays the current directory
Name                : loc
CommandType         : Alias
```

O `Set-Alias` cmdlet cria um alias na sessão atual do PowerShell. O parâmetro **Name** especifica o nome do alias, `loc` . O parâmetro **Value** especifica o `Get-Location` cmdlet que o alias executa. O parâmetro **Option** especifica o valor **ReadOnly** . O parâmetro **PassThru** representa o objeto alias e envia o objeto por meio do pipeline para o `Format-List` cmdlet. `Format-List` usa o parâmetro **Property** com um asterisco ( `*` ) para que todas as propriedades sejam exibidas. A saída de exemplo mostra uma lista parcial dessas propriedades.

O `loc` alias é alterado com a adição de dois parâmetros. **Descrição** adiciona texto para explicar a finalidade do alias. O parâmetro **Force** é necessário porque o `loc` alias é somente leitura. Se o parâmetro **Force** não for usado, a alteração falhará.

### Exemplo 4: criar um alias para um arquivo executável

Este exemplo cria um alias para um arquivo executável no computador local.

```
PS> Set-Alias -Name np -Value C:\Windows\notepad.exe

PS> Get-Alias -Name np

CommandType     Name
-----------     ----
Alias           np -> notepad.exe
```

O `Set-Alias` cmdlet cria um alias na sessão atual do PowerShell. O parâmetro **Name** especifica o nome do alias, `np` . O parâmetro **Value** especifica o caminho e o nome do aplicativo **C:\Windows\notepad.exe** . O `Get-Alias` cmdlet usa o parâmetro **Name** para mostrar que o `np` alias está associado a **notepad.exe** .

Para executar o alias, digite `np` na linha de comando do PowerShell para abrir **notepad.exe** .

### Exemplo 5: criar um alias para um comando com parâmetros

Este exemplo mostra como atribuir um alias a um comando com parâmetros.

Você pode criar um alias para um cmdlet, como `Set-Location` . Você não pode criar um alias para um comando com parâmetros e valores, como `Set-Location -Path C:\Windows\System32` . Para criar um alias para um comando, crie uma função que inclua o comando e, em seguida, crie um alias para a função. Para obter mais informações, consulte [about_Functions](../Microsoft.PowerShell.Core/about/about_Functions.md).

```
PS> Function CD32 {Set-Location -Path C:\Windows\System32}

PS> Set-Alias -Name Go -Value CD32
```

Uma função chamada `CD32` é criada. A função usa o `Set-Location` cmdlet com o parâmetro **Path** para especificar o diretório, **C:\Windows\System32** .

O `Set-Alias` cmdlet cria um alias para a função na sessão atual do PowerShell. O parâmetro **Name** especifica o nome do alias, `Go` . O parâmetro **Value** especifica o nome da função, `CD32` .

Para executar o alias, digite `Go` na linha de comando do PowerShell. A `CD32` função é executada e muda para o diretório **C:\Windows\System32** .

## PARAMETERS

### -Description

Especifica uma descrição do alias. Você pode digitar qualquer cadeia de caracteres. Se a descrição incluir espaços, coloque-o entre aspas simples.

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

### -Force

Use o parâmetro **Force** para alterar ou excluir um alias que tenha o parâmetro **Option** definido como **ReadOnly** .

O parâmetro **Force** não pode alterar nem excluir um alias com o parâmetro **Option** definido como **Constant** .

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

### -Name

Especifica o nome de um novo alias. Um nome de alias pode conter caracteres alfanuméricos e hifens. Nomes de alias não podem ser numéricos, como 123.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Opção

Define o valor da propriedade de **opção** do alias. Valores como **ReadOnly** e **Constant** protegem um alias de alterações involuntárias. Para ver a propriedade **Option** de todos os aliases na sessão, digite `Get-Alias | Format-Table -Property Name, Options -Autosize` .

Os valores aceitáveis para esse parâmetro são os seguintes:

- **Escopo** O alias é copiado para todos os novos escopos criados.
- **Constante** Não pode ser alterado ou excluído.
- **Nenhum** Não define opções e é o padrão.
- **Particular** O alias está disponível somente no escopo atual.
- **Somente leitura** Não pode ser alterado ou excluído, a menos que o parâmetro **Force** seja usado.
- **Não especificado**

```yaml
Type: System.Management.Automation.ScopedItemOptions
Parameter Sets: (All)
Aliases:
Accepted values: AllScope, Constant, None, Private, ReadOnly, Unspecified

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Retorna um objeto que representa o alias. Use um cmdlet Format como `Format-List` para exibir o objeto. Por padrão, `Set-Alias` o não gera nenhuma saída.

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

### -Escopo

Especifica o escopo no qual esse alias é válido. O valor padrão é **local** . Para obter mais informações, consulte [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).

Os valores aceitáveis são os seguintes:

- Global
- Local
- Privados
- Escopos numerados
- script

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Global, Local, Private, Numbered scopes, Script

Required: False
Position: Named
Default value: Local
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value

Especifica o nome do cmdlet ou comando que o alias executa. O parâmetro de **valor** é a propriedade de **definição** do alias.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm

Solicita sua confirmação antes de executar o cmdlet.

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

Mostra o que aconteceria se o cmdlet fosse executado. O cmdlet não é executado.

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

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### Nenhum

`Set-Alias` Não aceita a entrada do pipeline.

## SAÍDAS

### Nenhum ou System. Management. Automation. AliasInfo

Quando você usa o parâmetro **PassThru** , o `Set-Alias` gera um objeto **System. Management. Automation. AliasInfo** que representa o alias. Caso contrário, `Set-Alias` o não gera nenhuma saída.

## OBSERVAÇÕES

O PowerShell inclui aliases internos que estão disponíveis em cada sessão do PowerShell. O `Get-Alias` cmdlet exibe os aliases disponíveis em uma sessão do PowerShell.

Para criar um alias, use os cmdlets `Set-Alias` ou `New-Alias` . No PowerShell 6, para excluir um alias, use o `Remove-Alias` cmdlet. `Remove-Item` é aceita para compatibilidade com versões anteriores do PowerShell, por exemplo, para scripts criados Use um comando como `Remove-Item -Path Alias:aliasname` .

Para criar um alias que esteja disponível em cada sessão do PowerShell, adicione-o ao seu perfil do PowerShell.
Para obter mais informações, consulte [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).

Um alias pode ser salvo e reutilizado em outra sessão do PowerShell fazendo uma exportação e uma importação. Para salvar um alias em um arquivo, use `Export-Alias` . Para adicionar um alias salvo a uma nova sessão do PowerShell, use `Import-Alias` .

## LINKS RELACIONADOS

[about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[about_Functions](../Microsoft.PowerShell.Core/about/about_Functions.md)

[about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md)

[about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md)

[Export-Alias](Export-Alias.md)

[Get-Alias](Get-Alias.md)

[Import-Alias](Import-Alias.md)

[New-Alias](New-Alias.md)

[Remove-Alias](Remove-Alias.md)

[Remove-Item](../Microsoft.PowerShell.Management/Remove-Item.md)
