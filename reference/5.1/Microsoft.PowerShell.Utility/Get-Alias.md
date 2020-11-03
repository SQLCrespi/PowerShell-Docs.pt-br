---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-alias?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Alias
ms.openlocfilehash: cf936b63063b3381c4aac54e246ec921b61c3b22
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193822"
---
# Get-Alias

## SINOPSE

Obtém os aliases para a sessão atual.

## SYNTAX

### Padrão (padrão)

```
Get-Alias [[-Name] <String[]>] [-Exclude <String[]>] [-Scope <String>]
 [<CommonParameters>]
```

### Definição

```
Get-Alias [-Exclude <String[]>] [-Scope <String>] [-Definition <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION

O cmdlet **Get-Alias** Obtém os aliases na sessão atual.
Isso inclui aliases internos, aliases que você definiu ou importou e aliases que você adicionou ao seu perfil do PowerShell.

Por padrão, **Get-Alias** usa um alias e retorna o nome do comando.
Quando você usa o parâmetro de *definição* , **Get-Alias** usa um nome de comando e retorna seus aliases.

A partir do Windows PowerShell 3,0, **Get-Alias** exibe nomes de alias não hifenizados em um `<alias> -> <definition>` formato para facilitar ainda mais a localização das informações necessárias.

## EXEMPLOS

### Exemplo 1: obter todos os aliases na sessão atual

```
PS C:\> Get-Alias

CommandType     Name
-----------     ----
Alias           % -> ForEach-Object
Alias           ? -> Where-Object
Alias           ac -> Add-Content
Alias           asnp -> Add-PSSnapin
Alias           cat -> Get-Content
Alias           cd -> Set-Location
Alias           chdir -> Set-Location
Alias           clc -> Clear-Content
Alias           clear -> Clear-Host
Alias           clhy -> Clear-History
...
```

Este comando obtém todos os aliases na sessão atual.

A saída mostra o `<alias> -> <definition>` formato que foi introduzido no Windows PowerShell 3,0.
Esse formato é usado apenas para aliases que não incluem hifens, pois aliases com hifens são geralmente nomes preferidos de cmdlets e funções, em vez de apelidos.

### Exemplo 2: obter aliases por nome

```powershell
Get-Alias -Name gp*, sp* -Exclude *ps
```

Esse comando obtém todos os aliases que começam com GP ou SP, exceto para aliases que terminam com PS.

### Exemplo 3: obter aliases para um cmdlet

```powershell
Get-Alias -Definition Get-ChildItem
```

Este comando obtém os aliases para o cmdlet Get-ChildItem.

Por padrão, o cmdlet **Get-Alias** Obtém o nome do item quando você conhece o alias.
O parâmetro de *definição* Obtém o alias quando você sabe o nome do item.

### Exemplo 4: obter aliases por Propriedade

```powershell
Get-Alias | Where-Object {$_.Options -Match "ReadOnly"}
```

Esse comando obtém todos os aliases nos quais o valor da Propriedade Options é ReadOnly.
Esse comando fornece uma maneira rápida de localizar os aliases que são criados no PowerShell, pois eles têm a opção ReadOnly.

Options é apenas uma propriedade dos objetos AliasInfo que **Get-Alias** obtém.
Para localizar todas as propriedades e métodos de objetos AliasInfo, digite `Get-Alias | get-member` .

### Exemplo 5: obter aliases por nome e filtro por letra inicial

```powershell
Get-Alias -Definition "*-PSSession" -Exclude e* -Scope Global
```

Este exemplo obtém aliases para comandos com nomes que terminam em "-PSSession", exceto para aqueles que começam com "e".

O comando usa o parâmetro *Scope* para aplicar o comando no escopo global.
Isso é útil em scripts quando você deseja obter os aliases na sessão.

## PARAMETERS

### -Definition

Obtém os aliases para o item especificado.
Digite o nome de um cmdlet, uma função, um script, um arquivo ou arquivo executável.

Esse parâmetro é chamado de *definição* , pois pesquisa o nome do item na propriedade definição do objeto alias.

```yaml
Type: System.String[]
Parameter Sets: Definition
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Excluir

Omite os itens especificados.
O valor desse parâmetro qualifica os parâmetros Name e Definition.
Digite um nome, uma definição ou um padrão, como "s *".
Caracteres curinga são permitidos.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Name

Especifica os aliases que esse cmdlet obtém.
Caracteres curinga são permitidos.
Por padrão, o `Get-Alias` recupera todos os aliases definidos para a sessão atual.
O **nome** do parâmetro é opcional.
Você também pode canalizar nomes de alias para `Get-Alias` .

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: False
Position: 0
Default value: All aliases
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Escopo

Especifica o escopo para o qual este cmdlet obtém aliases.
Os valores aceitáveis para esse parâmetro são:

- Global
- Local
- script
- Um número relativo ao escopo atual (0 até o número de escopos, em que 0 é o escopo atual e 1 é seu pai)

Local é o padrão.
Para obter mais informações, consulte about_Scopes.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System.String

Você pode canalizar nomes de alias para **Get-Alias** .

## SAÍDAS

### System. Management. Automation. AliasInfo

**Get-Alias** retorna um objeto que representa cada alias.
**Get-Alias** retorna o mesmo objeto para cada alias, mas o PowerShell usa um formato baseado em seta para exibir os nomes de aliases não-hifenizados.

## OBSERVAÇÕES

- Para criar um novo alias, use Set-Alias ou New-Alias. Para excluir um alias, use Remove-Item.
- O formato de nome de alias com base em seta não é usado para aliases que incluem um hífen. Eles devem ser nomes substitutos preferenciais para cmdlets e funções, em vez de abreviações típicas ou apelidos.

## LINKS RELACIONADOS

[Export-Alias](Export-Alias.md)

[Import-Alias](Import-Alias.md)

[New-Alias](New-Alias.md)

[Set-Alias](Set-Alias.md)

[Provedor Alias](../Microsoft.PowerShell.Core/About/about_Alias_Provider.md)

[about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)
