---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/update-list?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-List
ms.openlocfilehash: 00ada05f52967c0857cfad63a94cd23c49b69367
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2020
ms.locfileid: "93192940"
---
# Update-List

## SINOPSE
Adiciona e remove itens de um valor de propriedade que contém uma coleção de objetos.

## SYNTAX

### Addremoveset (padrão)

```
Update-List [-Add <Object[]>] [-Remove <Object[]>] [-InputObject <PSObject>] [[-Property] <String>]
 [<CommonParameters>]
```

### Replacem

```
Update-List -Replace <Object[]> [-InputObject <PSObject>] [[-Property] <String>] [<CommonParameters>]
```

## DESCRIPTION

O `Update-List` cmdlet adiciona, remove ou substitui itens em um valor de propriedade de um objeto e retorna o objeto atualizado. Esse cmdlet foi desenvolvido para propriedades que contêm coleções de objetos.

Os parâmetros **Adicionar** e **remover** adicionam itens individuais e os removem da coleção.
O parâmetro **replace** substitui toda a coleção.

Se você não especificar uma propriedade no comando, `Update-List` o retornará um objeto que descreve a atualização em vez de atualizar o objeto. Você pode enviar o objeto de atualização para os cmdlets que alteram objetos, como `Set` cmdlets.

Esse cmdlet funciona somente quando a propriedade que está sendo atualizada dá suporte à interface **IList** que `Update-List` usa o. Além disso, todos os `Set` cmdlets que aceitam uma atualização devem dar suporte à interface **IList** .

Os cmdlets principais instalados com o PowerShell não dão suporte a essa interface. Para determinar se há suporte a um cmdlet `Update-List` , consulte o tópico de ajuda do cmdlet.

Esse cmdlet foi reintroduzido no PowerShell 7.

## EXEMPLOS

### Exemplo 1: adicionar itens a um valor de propriedade

Neste exemplo, criamos uma classe que representa um baralho de cartas onde os cartões são armazenados como um objeto de coleção de **lista** . O método **NewDeck ()** usa `Update-List` para adicionar um baralho completo de valores de cartão à coleção de **cartões** .

```powershell
class Cards {

    [System.Collections.Generic.List[string]]$cards
    [string]$name

    Cards([string]$_name) {
        $this.name = $_name
        $this.cards = [System.Collections.Generic.List[string]]::new()
    }

    NewDeck() {
        $_suits = "`u{2663}","`u{2666}","`u{2665}","`u{2660}"
        $_values = 'A',2,3,4,5,6,7,8,9,10,'J','Q','K'
        $_deck = foreach ($s in $_suits){ foreach ($v in $_values){ "$v$s"} }
        $this | Update-List -Property cards -Add $_deck | Out-Null
    }

    Show() {
        Write-Host
        Write-Host $this.name ": " $this.cards[0..12]
        if ($this.cards.count -gt 13) {
            Write-Host (' ' * ($this.name.length+3)) $this.cards[13..25]
        }
        if ($this.cards.count -gt 26) {
            Write-Host (' ' * ($this.name.length+3)) $this.cards[26..38]
        }
        if ($this.cards.count -gt 39) {
            Write-Host (' ' * ($this.name.length+3)) $this.cards[39..51]
        }
    }

    Shuffle() { $this.cards = Get-Random -InputObject $this.cards -Count 52 }

    Sort() { $this.cards.Sort() }
}
```

> [!NOTE]
> O `Update-List` cmdlet gera o objeto atualizado para o pipeline. Canalizamos a saída para `Out-Null` para suprimir a exibição indesejada.

### Exemplo 2: Adicionar e remover itens de uma propriedade de coleção

Continuando com o código no exemplo 1, criaremos instâncias da classe de **cartões** para representar um baralho e cartões mantidos por dois jogadores. Usamos o `Update-List` cmdlet para adicionar cartões às mãos dos jogadores e remover cartões do baralho.

```powershell
$player1 = [Cards]::new('Player 1')
$player2 = [Cards]::new('Player 2')

$deck = [Cards]::new('Deck')
$deck.NewDeck()
$deck.Shuffle()
$deck.Show()

# Deal two hands
$player1 | Update-List -Property cards -Add $deck.cards[0,2,4,6,8] | Out-Null
$player2 | Update-List -Property cards -Add $deck.cards[1,3,5,7,9] | Out-Null
$deck | Update-List -Property cards -Remove $player1.cards | Out-Null
$deck | Update-List -Property cards -Remove $player2.cards | Out-Null

$player1.Show()
$player2.Show()
$deck.Show()
```

```Output
Deck :  4♦ 7♥ J♦ 5♣ A♣ 8♦ J♣ Q♥ 6♦ 3♦ 9♦ 6♣ 2♣
        K♥ 4♠ 10♥ 8♠ 10♦ 9♠ 6♠ K♦ 7♣ 3♣ Q♣ A♥ Q♠
        3♥ 5♥ 2♦ 5♠ J♥ J♠ 10♣ 4♥ Q♦ 10♠ 4♣ 2♠ 2♥
        6♥ 7♦ A♠ 5♦ 8♣ 9♥ K♠ 7♠ 3♠ 9♣ A♦ K♣ 8♥

Player 1 :  4♦ J♦ A♣ J♣ 6♦

Player 2 :  7♥ 5♣ 8♦ Q♥ 3♦

Deck :  9♦ 6♣ 2♣ K♥ 4♠ 10♥ 8♠ 10♦ 9♠ 6♠ K♦ 7♣ 3♣
        Q♣ A♥ Q♠ 3♥ 5♥ 2♦ 5♠ J♥ J♠ 10♣ 4♥ Q♦ 10♠
        4♣ 2♠ 2♥ 6♥ 7♦ A♠ 5♦ 8♣ 9♥ K♠ 7♠ 3♠ 9♣
        A♦ K♣ 8♥
```

A saída mostra o estado do baralho antes que os cartões fossem tratados para os jogadores. Você pode ver que cada jogador recebeu cinco cartas do baralho. A saída final mostra o estado do baralho depois de lidar com os cartões para os jogadores. `Update-List` foi usado para selecionar os cartões do baralho e adicioná-los à coleção de jogadores. Em seguida, as cartas dos jogadores foram removidas do baralho usando `Update-List` .

### Exemplo 3: Adicionar e remover itens em um único comando

`Update-List` permite que você use os parâmetros **Add** e **Remove** em um único comando. Neste exemplo, o jogador 1 deseja descartar `4♦` e `6♦` obter dois novos cartões.

```powershell
# Player 1 wants two new cards - remove 2 cards & add 2 cards
$player1 | Update-List -Property cards -Remove $player1.cards[0,4] -Add $deck.cards[0..1] | Out-Null
$player1.Show()

# remove dealt cards from deck
$deck | Update-List -Property cards -Remove $deck.cards[0..1] | Out-Null
$deck.Show()
```

```Output
Player 1 :  J♦ A♣ J♣ 9♦ 6♣

Deck :  2♣ K♥ 4♠ 10♥ 8♠ 10♦ 9♠ 6♠ K♦ 7♣ 3♣ Q♣ A♥
        Q♠ 3♥ 5♥ 2♦ 5♠ J♥ J♠ 10♣ 4♥ Q♦ 10♠ 4♣ 2♠
        2♥ 6♥ 7♦ A♠ 5♦ 8♣ 9♥ K♠ 7♠ 3♠ 9♣ A♦ K♣
        8♥
```

## PARAMETERS

### -Add

Especifica os valores de propriedade a ser adicionado à coleção. Insira os valores na ordem em que eles devem aparecer na coleção.

```yaml
Type: System.Object[]
Parameter Sets: AddRemoveSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Especifica os objetos a serem atualizados. Também é possível canalizar o objeto a ser atualizado para `Update-List` .

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

### -Propriedade

Especifica a propriedade que contém a coleção que está sendo atualizada. Se você omitir esse parâmetro, `Update-List` retornará um objeto que representa a alteração em vez de alterar o objeto.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Remove

Especifica os valores de propriedade a serem removidos da coleção.

```yaml
Type: System.Object[]
Parameter Sets: AddRemoveSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Substituir

Especifica uma nova coleção. Esse parâmetro substitui todos os itens na coleção original com os itens especificados por esse parâmetro.

```yaml
Type: System.Object[]
Parameter Sets: ReplaceSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable. Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## ENTRADAS

### System. Management. Automation. PSObject

Você pode canalizar os objetos a serem atualizados para o `Update-List` .

## SAÍDAS

### Objetos ou System. Management. Automation. PSListModifier

`Update-List` Retorna o objeto atualizado ou retorna um objeto que representa a ação de atualização.

## OBSERVAÇÕES

## LINKS RELACIONADOS

[Format-List](Format-List.md)

[Select-Object](Select-Object.md)
