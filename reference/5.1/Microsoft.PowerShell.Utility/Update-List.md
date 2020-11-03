---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell, cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/update-list?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-List
ms.openlocfilehash: eccee5ad302395116430006ed4dc0395946696b6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "93193722"
---
# <span data-ttu-id="dba48-103">Update-List</span><span class="sxs-lookup"><span data-stu-id="dba48-103">Update-List</span></span>

## <span data-ttu-id="dba48-104">SINOPSE</span><span class="sxs-lookup"><span data-stu-id="dba48-104">SYNOPSIS</span></span>
<span data-ttu-id="dba48-105">Adiciona e remove itens de um valor de propriedade que contém uma coleção de objetos.</span><span class="sxs-lookup"><span data-stu-id="dba48-105">Adds items to and removes items from a property value that contains a collection of objects.</span></span>

## <span data-ttu-id="dba48-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dba48-106">SYNTAX</span></span>

### <span data-ttu-id="dba48-107">Addremoveset (padrão)</span><span class="sxs-lookup"><span data-stu-id="dba48-107">AddRemoveSet (Default)</span></span>

```
Update-List [-Add <Object[]>] [-Remove <Object[]>] [-InputObject <PSObject>] [[-Property] <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="dba48-108">Replacem</span><span class="sxs-lookup"><span data-stu-id="dba48-108">ReplaceSet</span></span>

```
Update-List -Replace <Object[]> [-InputObject <PSObject>] [[-Property] <String>] [<CommonParameters>]
```

## <span data-ttu-id="dba48-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="dba48-109">DESCRIPTION</span></span>

<span data-ttu-id="dba48-110">O `Update-List` cmdlet adiciona, remove ou substitui itens em um valor de propriedade de um objeto e retorna o objeto atualizado.</span><span class="sxs-lookup"><span data-stu-id="dba48-110">The `Update-List` cmdlet adds, removes, or replaces items in a property value of an object and returns the updated object.</span></span> <span data-ttu-id="dba48-111">Esse cmdlet foi desenvolvido para propriedades que contêm coleções de objetos.</span><span class="sxs-lookup"><span data-stu-id="dba48-111">This cmdlet is designed for properties that contain collections of objects.</span></span>

<span data-ttu-id="dba48-112">Os parâmetros **Adicionar** e **remover** adicionam itens individuais e os removem da coleção.</span><span class="sxs-lookup"><span data-stu-id="dba48-112">The **Add** and **Remove** parameters add individual items to and remove them from the collection.</span></span>
<span data-ttu-id="dba48-113">O parâmetro **replace** substitui toda a coleção.</span><span class="sxs-lookup"><span data-stu-id="dba48-113">The **Replace** parameter replaces the entire collection.</span></span>

<span data-ttu-id="dba48-114">Se você não especificar uma propriedade no comando, `Update-List` o retornará um objeto que descreve a atualização em vez de atualizar o objeto.</span><span class="sxs-lookup"><span data-stu-id="dba48-114">If you do not specify a property in the command, `Update-List` returns an object that describes the update instead of updating the object.</span></span> <span data-ttu-id="dba48-115">Você pode enviar o objeto de atualização para os cmdlets que alteram objetos, como `Set` cmdlets.</span><span class="sxs-lookup"><span data-stu-id="dba48-115">You can submit the update object to cmdlets that change objects, such as `Set` cmdlets.</span></span>

<span data-ttu-id="dba48-116">Esse cmdlet funciona somente quando a propriedade que está sendo atualizada dá suporte à interface **IList** que `Update-List` usa o.</span><span class="sxs-lookup"><span data-stu-id="dba48-116">This cmdlet works only when the property that is being updated supports the **IList** interface that `Update-List` uses.</span></span> <span data-ttu-id="dba48-117">Além disso, todos os `Set` cmdlets que aceitam uma atualização devem dar suporte à interface **IList** .</span><span class="sxs-lookup"><span data-stu-id="dba48-117">Also, any `Set` cmdlets that accept an update must support the **IList** interface.</span></span>

<span data-ttu-id="dba48-118">Os cmdlets principais instalados com o PowerShell não dão suporte a essa interface.</span><span class="sxs-lookup"><span data-stu-id="dba48-118">The core cmdlets that are installed with PowerShell do not support this interface.</span></span> <span data-ttu-id="dba48-119">Para determinar se há suporte a um cmdlet `Update-List` , consulte o tópico de ajuda do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="dba48-119">To determine whether a cmdlet supports `Update-List`, see the cmdlet Help topic.</span></span>

## <span data-ttu-id="dba48-120">EXEMPLOS</span><span class="sxs-lookup"><span data-stu-id="dba48-120">EXAMPLES</span></span>

### <span data-ttu-id="dba48-121">Exemplo 1: adicionar itens a um valor de propriedade</span><span class="sxs-lookup"><span data-stu-id="dba48-121">Example 1: Add items to a property value</span></span>

<span data-ttu-id="dba48-122">Neste exemplo, criamos uma classe que representa um baralho de cartas onde os cartões são armazenados como um objeto de coleção de **lista** .</span><span class="sxs-lookup"><span data-stu-id="dba48-122">In this example we create a class that represents a deck of cards where the cards are stored as a **List** collection object.</span></span> <span data-ttu-id="dba48-123">O método **NewDeck ()** usa `Update-List` para adicionar um baralho completo de valores de cartão à coleção de **cartões** .</span><span class="sxs-lookup"><span data-stu-id="dba48-123">The **NewDeck()** method uses `Update-List`to add a complete deck of card values to the **cards** collection.</span></span>

```powershell
class Cards {

    [System.Collections.Generic.List[string]]$cards
    [string]$name

    Cards([string]$_name) {
        $this.name = $_name
        $this.cards = [System.Collections.Generic.List[string]]::new()
    }

    NewDeck() {
        $_suits = [char]0x2663,[char]0x2666,[char]0x2665,[char]0x2660
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
> <span data-ttu-id="dba48-124">O `Update-List` cmdlet gera o objeto atualizado para o pipeline.</span><span class="sxs-lookup"><span data-stu-id="dba48-124">The `Update-List` cmdlet outputs the updated object to the pipeline.</span></span> <span data-ttu-id="dba48-125">Canalizamos a saída para `Out-Null` para suprimir a exibição indesejada.</span><span class="sxs-lookup"><span data-stu-id="dba48-125">We pipe the output to `Out-Null` to suppress the unwanted display.</span></span>

### <span data-ttu-id="dba48-126">Exemplo 2: Adicionar e remover itens de uma propriedade de coleção</span><span class="sxs-lookup"><span data-stu-id="dba48-126">Example 2: Add and remove items of a collection property</span></span>

<span data-ttu-id="dba48-127">Continuando com o código no exemplo 1, criaremos instâncias da classe de **cartões** para representar um baralho e cartões mantidos por dois jogadores.</span><span class="sxs-lookup"><span data-stu-id="dba48-127">Continuing with the code in Example 1, we will create instances of the **Cards** class to represent a deck of cards and the cards held by two players.</span></span> <span data-ttu-id="dba48-128">Usamos o `Update-List` cmdlet para adicionar cartões às mãos dos jogadores e remover cartões do baralho.</span><span class="sxs-lookup"><span data-stu-id="dba48-128">We use the `Update-List` cmdlet to add cards to the players' hands and to remove cards from the deck.</span></span>

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

<span data-ttu-id="dba48-129">A saída mostra o estado do baralho antes que os cartões fossem tratados para os jogadores.</span><span class="sxs-lookup"><span data-stu-id="dba48-129">The output shows the state of the deck before the cards were dealt to the players.</span></span> <span data-ttu-id="dba48-130">Você pode ver que cada jogador recebeu cinco cartas do baralho.</span><span class="sxs-lookup"><span data-stu-id="dba48-130">You can see that each player received five cards from the deck.</span></span> <span data-ttu-id="dba48-131">A saída final mostra o estado do baralho depois de lidar com os cartões para os jogadores.</span><span class="sxs-lookup"><span data-stu-id="dba48-131">The final output shows the state of the deck after dealing the cards to the players.</span></span> <span data-ttu-id="dba48-132">`Update-List` foi usado para selecionar os cartões do baralho e adicioná-los à coleção de jogadores.</span><span class="sxs-lookup"><span data-stu-id="dba48-132">`Update-List` was used to select the cards from the deck and add them to the players' collection.</span></span> <span data-ttu-id="dba48-133">Em seguida, as cartas dos jogadores foram removidas do baralho usando `Update-List` .</span><span class="sxs-lookup"><span data-stu-id="dba48-133">Then the players' cards were removed from the deck using `Update-List`.</span></span>

### <span data-ttu-id="dba48-134">Exemplo 3: Adicionar e remover itens em um único comando</span><span class="sxs-lookup"><span data-stu-id="dba48-134">Example 3: Add and remove items in a single command</span></span>

<span data-ttu-id="dba48-135">`Update-List` permite que você use os parâmetros **Add** e **Remove** em um único comando.</span><span class="sxs-lookup"><span data-stu-id="dba48-135">`Update-List` allows you to use the **Add** and **Remove** parameters in a single command.</span></span> <span data-ttu-id="dba48-136">Neste exemplo, o jogador 1 deseja descartar `4♦` e `6♦` obter dois novos cartões.</span><span class="sxs-lookup"><span data-stu-id="dba48-136">In this example, Player 1 wants to discard the `4♦` and `6♦` and get two new cards.</span></span>

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

## <span data-ttu-id="dba48-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dba48-137">PARAMETERS</span></span>

### <span data-ttu-id="dba48-138">-Add</span><span class="sxs-lookup"><span data-stu-id="dba48-138">-Add</span></span>

<span data-ttu-id="dba48-139">Especifica os valores de propriedade a ser adicionado à coleção.</span><span class="sxs-lookup"><span data-stu-id="dba48-139">Specifies the property values to be added to the collection.</span></span> <span data-ttu-id="dba48-140">Insira os valores na ordem em que eles devem aparecer na coleção.</span><span class="sxs-lookup"><span data-stu-id="dba48-140">Enter the values in the order that they should appear in the collection.</span></span>

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

### <span data-ttu-id="dba48-141">-InputObject</span><span class="sxs-lookup"><span data-stu-id="dba48-141">-InputObject</span></span>

<span data-ttu-id="dba48-142">Especifica os objetos a serem atualizados.</span><span class="sxs-lookup"><span data-stu-id="dba48-142">Specifies the objects to be updated.</span></span> <span data-ttu-id="dba48-143">Também é possível canalizar o objeto a ser atualizado para `Update-List` .</span><span class="sxs-lookup"><span data-stu-id="dba48-143">You can also pipe the object to be updated to `Update-List`.</span></span>

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

### <span data-ttu-id="dba48-144">-Propriedade</span><span class="sxs-lookup"><span data-stu-id="dba48-144">-Property</span></span>

<span data-ttu-id="dba48-145">Especifica a propriedade que contém a coleção que está sendo atualizada.</span><span class="sxs-lookup"><span data-stu-id="dba48-145">Specifies the property that contains the collection that is being updated.</span></span> <span data-ttu-id="dba48-146">Se você omitir esse parâmetro, `Update-List` retornará um objeto que representa a alteração em vez de alterar o objeto.</span><span class="sxs-lookup"><span data-stu-id="dba48-146">If you omit this parameter, `Update-List` returns an object that represents the change instead of changing the object.</span></span>

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

### <span data-ttu-id="dba48-147">-Remove</span><span class="sxs-lookup"><span data-stu-id="dba48-147">-Remove</span></span>

<span data-ttu-id="dba48-148">Especifica os valores de propriedade a serem removidos da coleção.</span><span class="sxs-lookup"><span data-stu-id="dba48-148">Specifies the property values to be removed from the collection.</span></span>

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

### <span data-ttu-id="dba48-149">-Substituir</span><span class="sxs-lookup"><span data-stu-id="dba48-149">-Replace</span></span>

<span data-ttu-id="dba48-150">Especifica uma nova coleção.</span><span class="sxs-lookup"><span data-stu-id="dba48-150">Specifies a new collection.</span></span> <span data-ttu-id="dba48-151">Esse parâmetro substitui todos os itens na coleção original com os itens especificados por esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="dba48-151">This parameter replaces all items in the original collection with the items specified by this parameter.</span></span>

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

### <span data-ttu-id="dba48-152">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="dba48-152">CommonParameters</span></span>

<span data-ttu-id="dba48-153">Este cmdlet oferece suporte aos parâmetros comuns: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction e -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="dba48-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dba48-154">Para obter mais informações, confira [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="dba48-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="dba48-155">ENTRADAS</span><span class="sxs-lookup"><span data-stu-id="dba48-155">INPUTS</span></span>

### <span data-ttu-id="dba48-156">System. Management. Automation. PSObject</span><span class="sxs-lookup"><span data-stu-id="dba48-156">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="dba48-157">Você pode canalizar os objetos a serem atualizados para o `Update-List` .</span><span class="sxs-lookup"><span data-stu-id="dba48-157">You can pipe the objects to be updated to `Update-List`.</span></span>

## <span data-ttu-id="dba48-158">SAÍDAS</span><span class="sxs-lookup"><span data-stu-id="dba48-158">OUTPUTS</span></span>

### <span data-ttu-id="dba48-159">Objetos ou System. Management. Automation. PSListModifier</span><span class="sxs-lookup"><span data-stu-id="dba48-159">Objects or System.Management.Automation.PSListModifier</span></span>

<span data-ttu-id="dba48-160">`Update-List` Retorna o objeto atualizado ou retorna um objeto que representa a ação de atualização.</span><span class="sxs-lookup"><span data-stu-id="dba48-160">`Update-List` returns the updated object, or it returns an object that represents the update action.</span></span>

## <span data-ttu-id="dba48-161">OBSERVAÇÕES</span><span class="sxs-lookup"><span data-stu-id="dba48-161">NOTES</span></span>

## <span data-ttu-id="dba48-162">LINKS RELACIONADOS</span><span class="sxs-lookup"><span data-stu-id="dba48-162">RELATED LINKS</span></span>

[<span data-ttu-id="dba48-163">Format-List</span><span class="sxs-lookup"><span data-stu-id="dba48-163">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="dba48-164">Select-Object</span><span class="sxs-lookup"><span data-stu-id="dba48-164">Select-Object</span></span>](Select-Object.md)
