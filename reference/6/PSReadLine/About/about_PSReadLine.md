---
description: O PSReadLine fornece uma experiência de edição de linha de comando aprimorada no console do PowerShell.
keywords: powershell
Locale: en-US
ms.date: 02/10/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/about/about_psreadline?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Sobre o PSReadLine
ms.openlocfilehash: 5b59ffcdfb35c2aa10f8e0caf3a3b365c5bcf93e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196257"
---
# <a name="psreadline"></a>PSReadLine

## <a name="about_psreadline"></a>about_PSReadLine

## <a name="short-description"></a>DESCRIÇÃO BREVE

O PSReadLine fornece uma experiência de edição de linha de comando aprimorada no console do PowerShell.

## <a name="long-description"></a>DESCRIÇÃO LONGA

O PSReadLine 2,0 fornece uma poderosa experiência de edição de linha de comando para o console do PowerShell. Ele fornece:

- Cor da sintaxe da linha de comando
- Uma indicação visual de erros de sintaxe
- Uma experiência de várias linhas melhor (edição e histórico)
- Associações de chave personalizáveis
- Modos cmd e Emacs
- Muitas opções de configuração
- Conclusão de estilo bash (opcional no modo cmd, padrão no modo Emacs)
- Emacs Yank/Kill-Ring
- "Word" com base no token do PowerShell movimentação e eliminação

As funções a seguir estão disponíveis na classe **[Microsoft. PowerShell. PSConsoleReadLine]** .

> [!NOTE]
> A partir do PowerShell 7,0, o PowerShell ignora o carregamento automático de PSReadLine no Windows se um programa de leitor de tela for detectado. Atualmente, o PSReadLine não funciona bem com os leitores de tela. A renderização e a formatação padrão do PowerShell 7,0 no Windows funcionam corretamente. Você pode carregar o módulo manualmente, se necessário.

## <a name="basic-editing-functions"></a>Funções de edição básicas

### <a name="abort"></a>Anular

Anular a ação atual, por exemplo, pesquisa de histórico incremental.

- Emacs `<Ctrl+g>`

### <a name="acceptandgetnext"></a>AcceptAndGetNext

Tentativa de executar a entrada atual. Se ele puder ser executado (como acceptable), então, relembre o próximo item do histórico na próxima vez que o ReadLine for chamado.

- Emacs `<Ctrl+o>`

### <a name="acceptline"></a>Aceitar

Tentativa de executar a entrada atual. Se a entrada atual estiver incompleta (por exemplo, faltam parênteses de fechamento, colchete ou aspas), o prompt de continuação será exibido na próxima linha e PSReadLine aguardará que as chaves editem a entrada atual.

- Cmd `<Enter>`
- Emacs `<Enter>`
- Modo de inserção de vi: `<Enter>`

### <a name="addline"></a>AddLine

O prompt de continuação é exibido na próxima linha e PSReadLine aguarda que as chaves editem a entrada atual. Isso é útil para inserir a entrada de várias linhas como um único comando, mesmo quando uma única linha é completa entrada por si só.

- Cmd `<Shift+Enter>`
- Emacs `<Shift+Enter>`
- Modo de inserção de vi: `<Shift+Enter>`
- Modo de comando vi: `<Shift+Enter>`

### <a name="backwarddeletechar"></a>BackwardDeleteChar

Exclua o caractere antes do cursor.

- Cmd: `<Backspace>` , `<Ctrl+h>`
- Emacs: `<Backspace>` , `<Ctrl+Backspace>` , `<Ctrl+h>`
- Modo de inserção de vi: `<Backspace>`
- Modo de comando vi: `<X>` , `<d,h>`

### <a name="backwarddeleteline"></a>BackwardDeleteLine

Como BackwardKillLine-exclui o texto do ponto para o início da linha, mas não coloca o texto excluído no Kill-Ring.

- Cmd `<Ctrl+Home>`
- Modo de inserção vi: `<Ctrl+u>` , `<Ctrl+Home>`
- Modo de comando vi: `<Ctrl+u>` , `<Ctrl+Home>` , `<d,0>`

### <a name="backwarddeleteword"></a>BackwardDeleteWord

Exclui a palavra anterior.

- Modo de comando vi: `<Ctrl+w>` , `<d,b>`

### <a name="backwardkillline"></a>BackwardKillLine

Limpe a entrada do início da entrada para o cursor. O texto limpo é colocado no Kill-Ring.

- Emacs: `<Ctrl+u>` , `<Ctrl+x,Backspace>`

### <a name="backwardkillword"></a>BackwardKillWord

Limpe a entrada do início da palavra atual para o cursor. Se o cursor estiver entre palavras, a entrada será apagada do início da palavra anterior para o cursor. O texto limpo é colocado no Kill-Ring.

- Cmd `<Ctrl+Backspace>`
- Emacs: `<Alt+Backspace>` , `<Escape,Backspace>`
- Modo de inserção de vi: `<Ctrl+Backspace>`
- Modo de comando vi: `<Ctrl+Backspace>`

### <a name="cancelline"></a>Cancelar

Cancele a entrada atual, deixando a entrada na tela, mas retorna de volta para o host para que o prompt seja avaliado novamente.

- Modo de inserção de vi: `<Ctrl+c>`
- Modo de comando vi: `<Ctrl+c>`

### <a name="copy"></a>Copiar

Copie a região selecionada para a área de transferência do sistema. Se nenhuma região for selecionada, copie a linha inteira.

- Cmd `<Ctrl+C>`

### <a name="copyorcancelline"></a>CopyOrCancelLine

Se o texto estiver selecionado, copie para a área de transferência, caso contrário, cancele a linha.

- Cmd `<Ctrl+c>`
- Emacs `<Ctrl+c>`

### <a name="cut"></a>Recortar

Excluir região selecionada colocando texto excluído na área de transferência do sistema.

- Cmd `<Ctrl+x>`

### <a name="deletechar"></a>DeleteChar

Exclua o caractere sob o cursor.

- Cmd `<Delete>`
- Emacs `<Delete>`
- Modo de inserção de vi: `<Delete>`
- Modo de comando vi: `<Delete>` ,, `<x>` `<d,l>` , `<d,Space>`

### <a name="deletecharorexit"></a>DeleteCharOrExit

Exclua o caractere sob o cursor ou, se a linha estiver vazia, saia do processo.

- Emacs `<Ctrl+d>`

### <a name="deleteendofword"></a>DeleteEndOfWord

Excluir até o final da palavra.

- Modo de comando vi: `<d,e>`

### <a name="deleteline"></a>DeleteLine

Exclui a linha atual, habilitando desfazer.

- Modo de comando vi: `<d,d>`

### <a name="deletelinetofirstchar"></a>DeleteLineToFirstChar

Exclui o texto do cursor para o primeiro caractere que não seja em branco da linha.

- Modo de comando vi: `<d,^>`

### <a name="deletetoend"></a>DeleteToEnd

Excluir até o fim da linha.

- Modo de comando vi: `<D>` , `<d,$>`

### <a name="deleteword"></a>DeleteWord

Excluir a próxima palavra.

- Modo de comando vi: `<d,w>`

### <a name="forwarddeleteline"></a>ForwardDeleteLine

Como ForwardKillLine-exclui o texto do ponto até o fim da linha, mas não coloca o texto excluído no Kill-Ring.

- Cmd `<Ctrl+End>`
- Modo de inserção de vi: `<Ctrl+End>`
- Modo de comando vi: `<Ctrl+End>`

### <a name="insertlineabove"></a>InsertLineAbove

Uma nova linha vazia é criada acima da linha atual, independentemente de onde o cursor está na linha atual. O cursor se move para o início da nova linha.

- Cmd `<Ctrl+Enter>`

### <a name="insertlinebelow"></a>InsertLineBelow

Uma nova linha vazia é criada abaixo da linha atual, independentemente de onde o cursor está na linha atual. O cursor se move para o início da nova linha.

- Cmd `<Shift+Ctrl+Enter>`

### <a name="invertcase"></a>InvertCase

Inverta o caso do caractere atual e mova para o próximo.

- Modo de comando vi: `<~>`

### <a name="killline"></a>Finalizar

Limpe a entrada do cursor até o fim da entrada. O texto limpo é colocado no Kill-Ring.

- Emacs `<Ctrl+k>`

### <a name="killregion"></a>KillRegion

Elimine o texto entre o cursor e a marca.

- A função está desassociada.

### <a name="killword"></a>KillWord

Limpe a entrada do cursor até o fim da palavra atual. Se o cursor estiver entre palavras, a entrada será apagada do cursor até o final da próxima palavra. O texto limpo é colocado no Kill-Ring.

- Cmd `<Ctrl+Delete>`
- Emacs: `<Alt+d>` , `<Escape,d>`
- Modo de inserção de vi: `<Ctrl+Delete>`
- Modo de comando vi: `<Ctrl+Delete>`

### <a name="paste"></a>Colar

Cole o texto da área de transferência do sistema.

- Cmd: `<Ctrl+v>` , `<Shift+Insert>`
- Modo de inserção de vi: `<Ctrl+v>`
- Modo de comando vi: `<Ctrl+v>`

> [!IMPORTANT]
> Ao usar a função **Paste** , todo o conteúdo do buffer da área de transferência é colado no buffer de entrada de PSReadLine. O buffer de entrada é passado para o analisador do PowerShell. A entrada colada usando o método de colagem de **clique com o botão direito** do aplicativo de console é copiada para o buffer de entrada, um caractere por vez. O buffer de entrada é passado para o analisador quando um caractere de nova linha é copiado. Portanto, a entrada é analisada uma linha por vez. A diferença entre os métodos de colagem resulta em um comportamento de execução diferente.

### <a name="pasteafter"></a>PasteAfter

Colar a área de transferência após o cursor, movendo o cursor para o final do texto colado.

- Modo de comando vi: `<p>`

### <a name="pastebefore"></a>PasteBefore

Cole a área de transferência antes do cursor, movendo o cursor para o final do texto colado.

- Modo de comando vi: `<P>`

### <a name="prependandaccept"></a>PrependAndAccept

Preceda um ' # ' e aceite a linha.

- Modo de comando vi: `<#>`

### <a name="redo"></a>Refazer

Desfazer um desfazer.

- Cmd `<Ctrl+y>`
- Modo de inserção de vi: `<Ctrl+y>`
- Modo de comando vi: `<Ctrl+y>`

### <a name="repeatlastcommand"></a>RepeatLastCommand

Repita a última modificação de texto.

- Modo de comando vi: `<.>`

### <a name="revertline"></a>Reverter

Reverte todas as entradas para a entrada atual.

- Cmd `<Escape>`
- Emacs: `<Alt+r>` , `<Escape,r>`

### <a name="shellbackwardkillword"></a>ShellBackwardKillWord

Limpe a entrada do início da palavra atual para o cursor. Se o cursor estiver entre palavras, a entrada será apagada do início da palavra anterior para o cursor. O texto limpo é colocado no Kill-Ring.

A função está desassociada.

### <a name="shellkillword"></a>ShellKillWord

Limpe a entrada do cursor até o fim da palavra atual. Se o cursor estiver entre palavras, a entrada será apagada do cursor até o final da próxima palavra. O texto limpo é colocado no Kill-Ring.

A função está desassociada.

### <a name="swapcharacters"></a>SwapCharacters

Troque o caractere atual e aquele anterior.

- Emacs `<Ctrl+t>`
- Modo de inserção de vi: `<Ctrl+t>`
- Modo de comando vi: `<Ctrl+t>`

### <a name="undo"></a>Desfazer

Desfazer uma edição anterior.

- Cmd `<Ctrl+z>`
- Emacs: `<Ctrl+_>` , `<Ctrl+x,Ctrl+u>`
- Modo de inserção de vi: `<Ctrl+z>`
- Modo de comando vi: `<Ctrl+z>` , `<u>`

### <a name="undoall"></a>UndoAll

Desfazer todas as edições anteriores para a linha.

- Modo de comando vi: `<U>`

### <a name="unixwordrubout"></a>UnixWordRubout

Limpe a entrada do início da palavra atual para o cursor. Se o cursor estiver entre palavras, a entrada será apagada do início da palavra anterior para o cursor. O texto limpo é colocado no Kill-Ring.

- Emacs `<Ctrl+w>`

### <a name="validateandacceptline"></a>ValidateAndAcceptLine

Tentativa de executar a entrada atual. Se a entrada atual estiver incompleta (por exemplo, faltam parênteses de fechamento, colchete ou aspas), o prompt de continuação será exibido na próxima linha e PSReadLine aguardará que as chaves editem a entrada atual.

- Emacs `<Ctrl+m>`

### <a name="viacceptline"></a>ViAcceptLine

Aceite a linha e alterne para o modo de inserção.

- Modo de comando vi: `<Enter>`

### <a name="viacceptlineorexit"></a>ViAcceptLineOrExit

Como DeleteCharOrExit no modo Emacs, mas aceita a linha em vez de excluir um caractere.

- Modo de inserção de vi: `<Ctrl+d>`
- Modo de comando vi: `<Ctrl+d>`

### <a name="viappendline"></a>ViAppendLine

Uma nova linha é inserida abaixo da linha atual.

- Modo de comando vi: `<o>`

### <a name="vibackwarddeleteglob"></a>ViBackwardDeleteGlob

Exclui a palavra anterior, usando apenas o espaço em branco como o delimitador de palavra.

- Modo de comando vi: `<d,B>`

### <a name="vibackwardglob"></a>ViBackwardGlob

Move o cursor de volta para o início da palavra anterior, usando apenas espaços em branco como delimitadores.

- Modo de comando vi: `<B>`

### <a name="videletebrace"></a>ViDeleteBrace

Localize a chave correspondente, o parêntese ou o colchete e exclua todo o conteúdo em, incluindo a chave.

- Modo de comando vi: `<d,%>`

### <a name="videleteendofglob"></a>ViDeleteEndOfGlob

Excluir até o final da palavra.

- Modo de comando vi: `<d,E>`

### <a name="videleteglob"></a>ViDeleteGlob

Exclua a próxima glob (palavra delimitada por espaço em branco).

- Modo de comando vi: `<d,W>`

### <a name="videletetobeforechar"></a>ViDeleteToBeforeChar

Exclui até o caractere especificado.

- Modo de comando vi: `<d,t>`

### <a name="videletetobeforecharbackward"></a>ViDeleteToBeforeCharBackward

Exclui até o caractere especificado.

- Modo de comando vi: `<d,T>`

### <a name="videletetochar"></a>ViDeleteToChar

Exclui até o caractere especificado.

- Modo de comando vi: `<d,f>`

### <a name="videletetocharbackward"></a>ViDeleteToCharBackward

Exclui até o caractere especificado.

- Modo de comando vi: `<d,F>`

### <a name="viinsertatbegining"></a>ViInsertAtBegining

Alterne para o modo de inserção e posicione o cursor no início da linha.

- Modo de comando vi: `<I>`

### <a name="viinsertatend"></a>ViInsertAtEnd

Alterne para o modo de inserção e posicione o cursor no final da linha.

- Modo de comando vi: `<A>`

### <a name="viinsertline"></a>ViInsertLine

Uma nova linha é inserida acima da linha atual.

- Modo de comando vi: `<O>`

### <a name="viinsertwithappend"></a>ViInsertWithAppend

Anexar da posição da linha atual.

- Modo de comando vi: `<a>`

### <a name="viinsertwithdelete"></a>ViInsertWithDelete

Exclua o caractere atual e alterne para o modo de inserção.

- Modo de comando vi: `<s>`

### <a name="vijoinlines"></a>ViJoinLines

Une a linha atual e a próxima linha.

- Modo de comando vi: `<J>`

### <a name="vireplaceline"></a>ViReplaceLine

Apague a linha de comando inteira.

- Modo de comando vi: `<S>` , `<c,c>`

### <a name="vireplacetobeforechar"></a>ViReplaceToBeforeChar

Substitui até o caractere especificado.

- Modo de comando vi: `<c,t>`

### <a name="vireplacetobeforecharbackward"></a>ViReplaceToBeforeCharBackward

Substitui até o caractere especificado.

- Modo de comando vi: `<c,T>`

### <a name="vireplacetochar"></a>ViReplaceToChar

Exclui até o caractere especificado.

- Modo de comando vi: `<c,f>`

### <a name="vireplacetocharbackward"></a>ViReplaceToCharBackward

Substitui até o caractere especificado.

- Modo de comando vi: `<c,F>`

### <a name="viyankbeginningofline"></a>ViYankBeginningOfLine

Yank desde o início do buffer até o cursor.

- Modo de comando vi: `<y,0>`

### <a name="viyankendofglob"></a>ViYankEndOfGlob

Yank do cursor até o fim das palavras.

- Modo de comando vi: `<y,E>`

### <a name="viyankendofword"></a>ViYankEndOfWord

Yank do cursor até o fim das palavras.

- Modo de comando vi: `<y,e>`

### <a name="viyankleft"></a>ViYankLeft

Yank caractere (s) à esquerda do cursor.

- Modo de comando vi: `<y,h>`

### <a name="viyankline"></a>ViYankLine

Yank todo o buffer.

- Modo de comando vi: `<y,y>`

### <a name="viyanknextglob"></a>ViYankNextGlob

Yank do cursor até o início da próxima palavra (s).

- Modo de comando vi: `<y,W>`

### <a name="viyanknextword"></a>ViYankNextWord

Yank as palavras após o cursor.

- Modo de comando vi: `<y,w>`

### <a name="viyankpercent"></a>ViYankPercent

Yank de/para a chave correspondente.

- Modo de comando vi: `<y,%>`

### <a name="viyankpreviousglob"></a>ViYankPreviousGlob

Yank do início das palavras ao cursor.

- Modo de comando vi: `<y,B>`

### <a name="viyankpreviousword"></a>ViYankPreviousWord

Yank as palavras antes do cursor.

- Modo de comando vi: `<y,b>`

### <a name="viyankright"></a>ViYankRight

Yank caractere (s) em e à direita do cursor.

- Modo de comando vi: `<y,l>` , `<y,Space>`

### <a name="viyanktoendofline"></a>ViYankToEndOfLine

Yank do cursor até o final do buffer.

- Modo de comando vi: `<y,$>`

### <a name="viyanktofirstchar"></a>ViYankToFirstChar

Yank do primeiro caractere que não seja espaço em branco para o cursor.

- Modo de comando vi: `<y,^>`

### <a name="yank"></a>Yank

Adicione o texto eliminado mais recentemente à entrada.

- Emacs `<Ctrl+y>`

### <a name="yanklastarg"></a>YankLastArg

Yank o último argumento da linha do histórico anterior. Com um argumento, a primeira vez que ele é invocado, se comporta da mesma forma que YankNthArg. Se invocado várias vezes, em vez disso, ele itera por meio de History e ARG define a direção (negativo inverte a direção.)

- Cmd `<Alt+.>`
- Emacs: `<Alt+.>` , `<Alt+_>` , `<Escape,.>` , `<Escape,_>`

### <a name="yankntharg"></a>YankNthArg

Yank o primeiro argumento (após o comando) da linha do histórico anterior.
Com um argumento, Yank o enésimo argumento (a partir de 0), se o argumento for negativo, inicie a partir do último argumento.

- Emacs: `<Ctrl+Alt+y>` , `<Escape,Ctrl+y>`

### <a name="yankpop"></a>YankPop

Se a operação anterior era Yank ou YankPop, substitua o texto arrancada anteriormente pelo próximo texto interrompido do Kill-Ring.

- Emacs: `<Alt+y>` , `<Escape,y>`

## <a name="cursor-movement-functions"></a>Funções de movimento do cursor

### <a name="backwardchar"></a>BackwardChar

Mover o cursor um caractere para a esquerda. Isso pode mover o cursor para a linha anterior de entrada de várias linhas.

- Cmd `<LeftArrow>`
- Emacs: `<LeftArrow>` , `<Ctrl+b>`
- Modo de inserção de vi: `<LeftArrow>`
- Modo de comando vi: `<LeftArrow>` , `<Backspace>` , `<h>`

### <a name="backwardword"></a>BackwardWord

Mover o cursor de volta para o início da palavra atual ou se estiver entre palavras, o início da palavra anterior. Os limites de palavras são definidos por um conjunto configurável de caracteres.

- Cmd `<Ctrl+LeftArrow>`
- Emacs: `<Alt+b>` , `<Escape,b>`
- Modo de inserção de vi: `<Ctrl+LeftArrow>`
- Modo de comando vi: `<Ctrl+LeftArrow>`

### <a name="beginningofline"></a>BeginningOfLine

Se a entrada tiver várias linhas, mover para o início da linha atual ou, se já estiver no início da linha, vá para o início da entrada. Se a entrada tiver uma única linha, vá para o início da entrada.

- Cmd `<Home>`
- Emacs: `<Home>` , `<Ctrl+a>`
- Modo de inserção de vi: `<Home>`
- Modo de comando vi: `<Home>`

### <a name="endofline"></a>EndOfLine

Se a entrada tiver várias linhas, mover para o final da linha atual ou, se já estiver no final da linha, mover para o final da entrada. Se a entrada tiver uma única linha, vá para o final da entrada.

- Cmd `<End>`
- Emacs: `<End>` , `<Ctrl+e>`
- Modo de inserção de vi: `<End>`

### <a name="forwardchar"></a>ForwardChar

Mover o cursor um caractere para a direita. Isso pode mover o cursor para a próxima linha de entrada de várias linhas.

- Cmd `<RightArrow>`
- Emacs: `<RightArrow>` , `<Ctrl+f>`
- Modo de inserção de vi: `<RightArrow>`
- Modo de comando vi: `<RightArrow>` , `<Space>` , `<l>`

### <a name="forwardword"></a>ForwardWord

Mover o cursor para o fim da palavra atual ou se estiver entre as palavras, até o final da próxima palavra. Os limites de palavras são definidos por um conjunto configurável de caracteres.

- Emacs: `<Alt+f>` , `<Escape,f>`

### <a name="gotobrace"></a>GotoBrace

Vá para a chave correspondente, parêntese ou colchete.

- Cmd `<Ctrl+]>`
- Modo de inserção de vi: `<Ctrl+]>`
- Modo de comando vi: `<Ctrl+]>`

### <a name="gotocolumn"></a>GotoColumn

Mova para a coluna indicada por ARG.

- Modo de comando vi: `<|>`

### <a name="gotofirstnonblankofline"></a>GotoFirstNonBlankOfLine

Mover o cursor para o primeiro caractere que não esteja em branco na linha.

- Modo de comando vi: `<^>`

### <a name="movetoendofline"></a>MoveToEndOfLine

Mover o cursor para o fim da entrada.

- Modo de comando vi: `<End>` , `<$>`

### <a name="nextline"></a>Próxima

Mover o cursor para a próxima linha.

- A função está desassociada.

### <a name="nextword"></a>NextWord

Mover o cursor para frente até o início da próxima palavra. Os limites de palavras são definidos por um conjunto configurável de caracteres.

- Cmd `<Ctrl+RightArrow>`
- Modo de inserção de vi: `<Ctrl+RightArrow>`
- Modo de comando vi: `<Ctrl+RightArrow>`

### <a name="nextwordend"></a>NextWordEnd

Mover o cursor para o fim da palavra atual ou se estiver entre as palavras, até o final da próxima palavra. Os limites de palavras são definidos por um conjunto configurável de caracteres.

- Modo de comando vi: `<e>`

### <a name="previousline"></a>Anterior

Mover o cursor para a linha anterior.

- A função está desassociada.

### <a name="shellbackwardword"></a>ShellBackwardWord

Mover o cursor de volta para o início da palavra atual ou se estiver entre palavras, o início da palavra anterior. Os limites de palavras são definidos por tokens do PowerShell.

- A função está desassociada.

### <a name="shellforwardword"></a>ShellForwardWord

Mover o cursor para frente até o início da próxima palavra. Os limites de palavras são definidos por tokens do PowerShell.

- A função está desassociada.

### <a name="shellnextword"></a>ShellNextWord

Mover o cursor para o fim da palavra atual ou se estiver entre as palavras, até o final da próxima palavra. Os limites de palavras são definidos por tokens do PowerShell.

- A função está desassociada.

### <a name="vibackwardword"></a>ViBackwardWord

Mover o cursor de volta para o início da palavra atual ou se estiver entre palavras, o início da palavra anterior. Os limites de palavras são definidos por um conjunto configurável de caracteres.

- Modo de comando vi: `<b>`

### <a name="viendofglob"></a>ViEndOfGlob

Move o cursor para o fim da palavra, usando apenas espaços em branco como delimitadores.

- Modo de comando vi: `<E>`

### <a name="viendofpreviousglob"></a>ViEndOfPreviousGlob

Move para o fim da palavra anterior, usando apenas o espaço em branco como um delimitador de palavra.

- A função está desassociada.

### <a name="vigotobrace"></a>ViGotoBrace

Semelhante a GotoBrace, mas é baseado em caractere em vez de baseado em token.

- Modo de comando vi: `<%>`

### <a name="vinextglob"></a>ViNextGlob

Move para a próxima palavra, usando apenas o espaço em branco como um delimitador de palavra.

- Modo de comando vi: `<W>`

### <a name="vinextword"></a>ViNextWord

Mover o cursor para frente até o início da próxima palavra. Os limites de palavras são definidos por um conjunto configurável de caracteres.

- Modo de comando vi: `<w>`

## <a name="history-functions"></a>Funções de histórico

### <a name="beginningofhistory"></a>BeginningOfHistory

Mover para o primeiro item no histórico.

- Emacs `<Alt+`<>`

### <a name="clearhistory"></a>ClearHistory

Limpa o histórico em PSReadLine. Isso não afeta o histórico do PowerShell.

- Cmd `<Alt+F7>`

### <a name="endofhistory"></a>EndOfHistory

Mover para o último item (a entrada atual) no histórico.

- Emacs `<Alt+>>`

### <a name="forwardsearchhistory"></a>ForwardSearchHistory

Execute uma pesquisa de encaminhamento incremental por meio do histórico.

- Cmd `<Ctrl+s>`
- Emacs `<Ctrl+s>`

### <a name="historysearchbackward"></a>HistorySearchBackward

Substitua a entrada atual pelo item ' Previous ' do histórico de PSReadLine que corresponde aos caracteres entre o início e a entrada e o cursor.

- Cmd `<F8>`

### <a name="historysearchforward"></a>HistorySearchForward

Substitua a entrada atual pelo item ' Next ' do histórico de PSReadLine que corresponde aos caracteres entre o início e a entrada e o cursor.

- Cmd `<Shift+F8>`

### <a name="nexthistory"></a>NextHistory

Substitua a entrada atual pelo item ' Next ' do histórico de PSReadLine.

- Cmd `<DownArrow>`
- Emacs: `<DownArrow>` , `<Ctrl+n>`
- Modo de inserção de vi: `<DownArrow>`
- Modo de comando vi: `<DownArrow>` , `<j>` , `<+>`

### <a name="previoushistory"></a>PreviousHistory

Substitua a entrada atual pelo item ' Previous ' do histórico de PSReadLine.

- Cmd `<UpArrow>`
- Emacs: `<UpArrow>` , `<Ctrl+p>`
- Modo de inserção de vi: `<UpArrow>`
- Modo de comando vi: `<UpArrow>` , `<k>` , `<->`

### <a name="reversesearchhistory"></a>ReverseSearchHistory

Execute uma pesquisa regressiva incremental por meio do histórico.

- Cmd `<Ctrl+r>`
- Emacs `<Ctrl+r>`

### <a name="visearchhistorybackward"></a>ViSearchHistoryBackward

Solicita uma cadeia de caracteres de pesquisa e inicia a pesquisa após a seqüência de aceitação.

- Modo de inserção de vi: `<Ctrl+r>`
- Modo de comando vi: `</>` , `<Ctrl+r>`

## <a name="completion-functions"></a>Funções de conclusão

### <a name="complete"></a>Concluir

Tentativa de executar a conclusão no texto ao redor do cursor. Se houver várias conclusões possíveis, o prefixo não ambíguo mais longo será usado para a conclusão. Se estiver tentando concluir a conclusão mais longa, não ambíguo, uma lista de conclusões possíveis será exibida.

- Emacs `<Tab>`

### <a name="menucomplete"></a>MenuComplete

Tentativa de executar a conclusão no texto ao redor do cursor. Se houver várias conclusões possíveis, o prefixo não ambíguo mais longo será usado para a conclusão. Se estiver tentando concluir a conclusão mais longa, não ambíguo, uma lista de conclusões possíveis será exibida.

- Cmd `<Ctrl+Space>`
- Emacs `<Ctrl+Space>`

### <a name="possiblecompletions"></a>PossibleCompletions

Exiba a lista de conclusões possíveis.

- Emacs `<Alt+=>`
- Modo de inserção de vi: `<Ctrl+Space>`
- Modo de comando vi: `<Ctrl+Space>`

### <a name="tabcompletenext"></a>TabCompleteNext

Tente concluir o texto ao redor do cursor com a próxima conclusão disponível.

- Cmd `<Tab>`
- Modo de comando vi: `<Tab>`

### <a name="tabcompleteprevious"></a>TabCompletePrevious

Tente concluir o texto ao redor do cursor com a conclusão disponível anterior.

- Cmd `<Shift+Tab>`
- Modo de comando vi: `<Shift+Tab>`

### <a name="vitabcompletenext"></a>ViTabCompleteNext

Encerra o grupo de edição atual, se necessário, e invoca TabCompleteNext.

- Modo de inserção de vi: `<Tab>`

### <a name="vitabcompleteprevious"></a>ViTabCompletePrevious

Encerra o grupo de edição atual, se necessário, e invoca TabCompletePrevious.

- Modo de inserção de vi: `<Shift+Tab>`

## <a name="miscellaneous-functions"></a>Funções diversas

### <a name="capturescreen"></a>CaptureScreen

Iniciar captura de tela interativa-setas para cima/para baixo Selecione linhas, insira copia o texto selecionado para a área de transferência como texto e HTML.

- A função está desassociada.

### <a name="clearscreen"></a>ClearScreen

Limpe a tela e desenhe a linha atual na parte superior da tela.

- Cmd `<Ctrl+l>`
- Emacs `<Ctrl+l>`
- Modo de inserção de vi: `<Ctrl+l>`
- Modo de comando vi: `<Ctrl+l>`

### <a name="digitargument"></a>DigitArgument

Inicie um novo argumento de dígito para passar para outras funções.

- Cmd: `<Alt+0>` ,,,,, `<Alt+1>` `<Alt+2>` `<Alt+3>` `<Alt+4>` `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`
- Emacs: `<Alt+0>` , `<Alt+1>` , `<Alt+2>` , `<Alt+3>` , `<Alt+4>` , `<Alt+5>` , `<Alt+6>` , `<Alt+7>` , `<Alt+8>` , `<Alt+9>` , `<Alt+->`
- Modo de comando vi:,,,,,, `<0>` `<1>` `<2>` `<3>` `<4>` `<5>` `<6>` , `<7>` , `<8>` , `<9>`

### <a name="invokeprompt"></a>InvokePrompt

Apaga o prompt atual e chama a função prompt para exibir novamente o prompt. Útil para manipuladores de chaves personalizadas que alteram o estado, por exemplo, alterar o diretório atual.

- A função está desassociada.

### <a name="scrolldisplaydown"></a>ScrollDisplayDown

Rolar a exibição uma tela para baixo.

- Cmd `<PageDown>`
- Emacs `<PageDown>`

### <a name="scrolldisplaydownline"></a>ScrollDisplayDownLine

Rolar a exibição uma linha para baixo.

- Cmd `<Ctrl+PageDown>`
- Emacs `<Ctrl+PageDown>`

### <a name="scrolldisplaytocursor"></a>ScrollDisplayToCursor

Rolar a exibição para o cursor.

- Emacs `<Ctrl+End>`

### <a name="scrolldisplaytop"></a>ScrollDisplayTop

Role a exibição para a parte superior.

- Emacs `<Ctrl+Home>`

### <a name="scrolldisplayup"></a>ScrollDisplayUp

Rolar a exibição uma tela para cima.

- Cmd `<PageUp>`
- Emacs `<PageUp>`

### <a name="scrolldisplayupline"></a>ScrollDisplayUpLine

Rolar a exibição uma linha para cima.

- Cmd `<Ctrl+PageUp>`
- Emacs `<Ctrl+PageUp>`

### <a name="selfinsert"></a>SelfInsert

Insira a chave.

- A função está desassociada.

### <a name="showkeybindings"></a>ShowKeyBindings

Mostrar todas as chaves associadas.

- Cmd `<Ctrl+Alt+?>`
- Emacs `<Ctrl+Alt+?>`
- Modo de inserção de vi: `<Ctrl+Alt+?>`

### <a name="vicommandmode"></a>ViCommandMode

Alterne o modo de operação atual de Vi-Insert para vi-Command.

- Modo de inserção de vi: `<Escape>`

### <a name="vidigitargumentinchord"></a>ViDigitArgumentInChord

Inicie um novo argumento de dígito para passar para outras funções enquanto estiver em uma das cordas do vi.

- A função está desassociada.

### <a name="vieditvisually"></a>ViEditVisually

Edite a linha de comando em um editor de texto especificado por $env: EDITOR ou $env: VISUAL.

- Emacs `<Ctrl+x,Ctrl+e>`
- Modo de comando vi: `<v>`

### <a name="viexit"></a>ViExit

Sai do Shell.

- A função está desassociada.

### <a name="viinsertmode"></a>ViInsertMode

Alterne para o modo de inserção.

- Modo de comando vi: `<i>`

### <a name="whatiskey"></a>WhatIsKey

Leia uma chave e diga-me a que a chave está associada.

- Cmd `<Alt+?>`
- Emacs `<Alt+?>`

## <a name="selection-functions"></a>Funções de seleção

### <a name="exchangepointandmark"></a>ExchangePointAndMark

O cursor é colocado no local da marca e a marca é movida para o local do cursor.

- Emacs `<Ctrl+x,Ctrl+x>`

### <a name="selectall"></a>SelectAll

Selecione a linha inteira.

- Cmd `<Ctrl+a>`

### <a name="selectbackwardchar"></a>SelectBackwardChar

Ajuste a seleção atual para incluir o caractere anterior.

- Cmd `<Shift+LeftArrow>`
- Emacs `<Shift+LeftArrow>`

### <a name="selectbackwardsline"></a>SelectBackwardsLine

Ajuste a seleção atual para incluir do cursor até o início da linha.

- Cmd `<Shift+Home>`
- Emacs `<Shift+Home>`

### <a name="selectbackwardword"></a>SelectBackwardWord

Ajuste a seleção atual para incluir a palavra anterior.

- Cmd `<Shift+Ctrl+LeftArrow>`
- Emacs `<Alt+B>`

### <a name="selectforwardchar"></a>SelectForwardChar

Ajuste a seleção atual para incluir o próximo caractere.

- Cmd `<Shift+RightArrow>`
- Emacs `<Shift+RightArrow>`

### <a name="selectforwardword"></a>SelectForwardWord

Ajuste a seleção atual para incluir a próxima palavra usando ForwardWord.

- Emacs `<Alt+F>`

### <a name="selectline"></a>Seleção

Ajuste a seleção atual para incluir do cursor até o fim da linha.

- Cmd `<Shift+End>`
- Emacs `<Shift+End>`

### <a name="selectnextword"></a>SelectNextWord

Ajuste a seleção atual para incluir a próxima palavra.

- Cmd `<Shift+Ctrl+RightArrow>`

### <a name="selectshellbackwardword"></a>SelectShellBackwardWord

Ajuste a seleção atual para incluir a palavra anterior usando ShellBackwardWord.

- A função está desassociada.

### <a name="selectshellforwardword"></a>SelectShellForwardWord

Ajuste a seleção atual para incluir a próxima palavra usando ShellForwardWord.

- A função está desassociada.

### <a name="selectshellnextword"></a>SelectShellNextWord

Ajuste a seleção atual para incluir a próxima palavra usando ShellNextWord.

- A função está desassociada.

### <a name="setmark"></a>Definir marca

Marque o local atual do cursor para uso em um comando de edição subsequente.

- Emacs `<Ctrl+`>`

## <a name="search-functions"></a>Funções de pesquisa

### <a name="charactersearch"></a>CharacterSearch

Ler um caractere e pesquisar a próxima ocorrência desse caractere.
Se um argumento for especificado, procure avançar (ou retroceder se negativo) para a enésima ocorrência.

- Cmd `<F3>`
- Emacs `<Ctrl+]>`
- Modo de inserção de vi: `<F3>`
- Modo de comando vi: `<F3>`

### <a name="charactersearchbackward"></a>CharacterSearchBackward

Ler um caractere e Pesquisar para a próxima ocorrência desse caractere. Se um argumento for especificado, pesquise retroativamente (ou encaminhe se negativo) para a enésima ocorrência.

- Cmd `<Shift+F3>`
- Emacs `<Ctrl+Alt+]>`
- Modo de inserção de vi: `<Shift+F3>`
- Modo de comando vi: `<Shift+F3>`

### <a name="repeatlastcharsearch"></a>RepeatLastCharSearch

Repita a última pesquisa de caractere gravada.

- Modo de comando vi: `<;>`

### <a name="repeatlastcharsearchbackwards"></a>RepeatLastCharSearchBackwards

Repita a última pesquisa de caractere gravada, mas na direção oposta.

- Modo de comando vi: `<,>`

### <a name="repeatsearch"></a>RepeatSearch

Repita a última pesquisa na mesma direção que antes.

- Modo de comando vi: `<n>`

### <a name="repeatsearchbackward"></a>RepeatSearchBackward

Repita a última pesquisa na mesma direção que antes.

- Modo de comando vi: `<N>`

### <a name="searchchar"></a>SearchChar

Ler o próximo caractere e, em seguida, encontrá-lo, avançar e, em seguida, voltar a usar um caractere. Isso é para a funcionalidade ' T'.

- Modo de comando vi: `<f>`

### <a name="searchcharbackward"></a>SearchCharBackward

Ler o próximo caractere e, em seguida, localizá-lo, retroceder e, em seguida, voltar um caractere. Isso é para a funcionalidade ' T'.

- Modo de comando vi: `<F>`

### <a name="searchcharbackwardwithbackoff"></a>SearchCharBackwardWithBackoff

Ler o próximo caractere e, em seguida, localizá-lo, retroceder e, em seguida, voltar um caractere. Isso é para a funcionalidade ' T'.

- Modo de comando vi: `<T>`

### <a name="searchcharwithbackoff"></a>SearchCharWithBackoff

Ler o próximo caractere e, em seguida, encontrá-lo, avançar e, em seguida, voltar a usar um caractere. Isso é para a funcionalidade ' T'.

- Modo de comando vi: `<t>`

### <a name="searchforward"></a>SearchForward

Solicita uma cadeia de caracteres de pesquisa e inicia a pesquisa após a seqüência de aceitação.

- Modo de inserção de vi: `<Ctrl+s>`
- Modo de comando vi: `<?>` , `<Ctrl+s>`

## <a name="custom-key-bindings"></a>Associações de chave personalizadas

O PSReadLine dá suporte a associações de chave personalizadas usando o cmdlet `Set-PSReadLineKeyHandler` . A maioria das associações de chave personalizadas chama uma das funções acima, por exemplo

```powershell
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
```

Você pode associar um ScriptBlock a uma chave. O ScriptBlock pode fazer praticamente qualquer coisa que você desejar. Alguns exemplos úteis incluem

- editar a linha de comando
- abrindo uma nova janela (por exemplo, ajuda)
- alterar os diretórios sem alterar a linha de comando

O ScriptBlock recebe dois argumentos:

- `$key` -Um objeto **[ConsoleKeyInfo]** que é a chave que disparou a associação personalizada. Se você associar o mesmo ScriptBlock a várias chaves e precisar executar ações diferentes dependendo da chave, poderá verificar $key. Muitas associações personalizadas ignoram esse argumento.

- `$arg` -Um argumento arbitrário. Geralmente, isso seria um argumento inteiro que o usuário passa das associações de chave DigitArgument. Se sua associação não aceitar argumentos, é razoável ignorar esse argumento.

Vamos dar uma olhada em um exemplo que adiciona uma linha de comando ao histórico sem executá-lo. Isso é útil quando você percebe que esqueceu de fazer algo, mas não quer inserir novamente a linha de comando que você já inseriu.

```powershell
$parameters = @{
    Key = 'Alt+w'
    BriefDescription = 'SaveInHistory'
    LongDescription = 'Save current line in history but do not execute'
    ScriptBlock = {
      param($key, $arg)   # The arguments are ignored in this example

      # GetBufferState gives us the command line (with the cursor position)
      $line = $null
      $cursor = $null
      [Microsoft.PowerShell.PSConsoleReadLine]::GetBufferState([ref]$line,
        [ref]$cursor)

      # AddToHistory saves the line in history, but does not execute it.
      [Microsoft.PowerShell.PSConsoleReadLine]::AddToHistory($line)

      # RevertLine is like pressing Escape.
      [Microsoft.PowerShell.PSConsoleReadLine]::RevertLine()
  }
}
Set-PSReadLineKeyHandler @parameters
```

Você pode ver muitos outros exemplos no arquivo `SamplePSReadLineProfile.ps1` que está instalado na pasta do módulo PSReadLine.

A maioria das associações de chave usa algumas funções auxiliares para editar a linha de comando.
Essas APIs são documentadas na próxima seção.

## <a name="custom-key-binding-support-apis"></a>APIs de suporte de associação de chave personalizada

As funções a seguir são públicas em Microsoft. PowerShell. PSConsoleReadLine, mas não podem ser associadas diretamente a uma chave. A maioria é útil em associações de chave personalizadas.

```csharp
void AddToHistory(string command)
```

Adicione uma linha de comando ao histórico sem executá-lo.

```csharp
void ClearKillRing()
```

Limpe o Kill-Ring.  Isso é usado principalmente para teste.

```csharp
void Delete(int start, int length)
```

Exclua os caracteres de comprimento do início.  Esta operação dá suporte a desfazer/refazer.

```csharp
void Ding()
```

Execute a ação de-Ding com base na preferência dos usuários.

```csharp
void GetBufferState([ref] string input, [ref] int cursor)
void GetBufferState([ref] Ast ast, [ref] Token[] tokens,
  [ref] ParseError[] parseErrors, [ref] int cursor)
```

Essas duas funções recuperam informações úteis sobre o estado atual do buffer de entrada.  A primeira é mais comumente usada para casos simples.  O segundo será usado se sua associação estiver fazendo algo mais avançado com a AST.

```csharp
IEnumerable[Microsoft.PowerShell.KeyHandler]
  GetKeyHandlers(bool includeBound, bool includeUnbound)

```

Essa função é usada pelo Get-PSReadLineKeyHandler e provavelmente não é útil em uma associação de chave personalizada.

```csharp
Microsoft.PowerShell.PSConsoleReadLineOptions GetOptions()
```

Essa função é usada pelo Get-PSReadLineOption e provavelmente não é muito útil em uma associação de chave personalizada.

```csharp
void GetSelectionState([ref] int start, [ref] int length)
```

Se não houver nenhuma seleção na linha de comando,-1 será retornado no início e no comprimento. Se houver uma seleção na linha de comando, o início e o comprimento da seleção serão retornados.

```csharp
void Insert(char c)
void Insert(string s)
```

Inserir um caractere ou uma cadeia de caracteres no cursor.  Esta operação dá suporte a desfazer/refazer.

```csharp
string ReadLine(runspace remoteRunspace,
  System.Management.Automation.EngineIntrinsics engineIntrinsics)
```

Esse é o ponto de entrada principal para PSReadLine. Ele não oferece suporte à recursão, portanto não é útil em uma associação de chave personalizada.

```csharp
void RemoveKeyHandler(string[] key)
```

Essa função é usada pelo Remove-PSReadLineKeyHandler e provavelmente não é muito útil em uma associação de chave personalizada.

```csharp
void Replace(int start, int length, string replacement)
```

Substitua algumas das entradas. Esta operação dá suporte a desfazer/refazer. Isso é preferível ao excluir seguido de Insert porque é tratado como uma única ação para desfazer.

```csharp
void SetCursorPosition(int cursor)
```

Mover o cursor para o deslocamento fornecido. O movimento do cursor não é rastreado para desfazer.

```csharp
void SetOptions(Microsoft.PowerShell.SetPSReadLineOption options)
```

Essa função é um método auxiliar usado pelo cmdlet Set-PSReadLineOption, mas pode ser útil para uma associação de chave personalizada que deseja alterar temporariamente uma configuração.

```csharp
bool TryGetArgAsInt(System.Object arg, [ref] int numericArg,
  int defaultNumericArg)
```

Esse método auxiliar é usado para associações personalizadas que respeitam DigitArgument. Uma chamada típica é parecida com

```powershell
[int]$numericArg = 0
[Microsoft.PowerShell.PSConsoleReadLine]::TryGetArgAsInt($arg,
  [ref]$numericArg, 1)
```

## <a name="note"></a>OBSERVAÇÃO

### <a name="powershell-compatibility"></a>COMPATIBILIDADE DO POWERSHELL

O PSReadLine requer o PowerShell 3,0 ou mais recente e o host do console. Ele não funciona no ISE do PowerShell. Ele funciona no console do Visual Studio Code.

### <a name="command-history"></a>HISTÓRICO DE COMANDOS

PSReadLine mantém um arquivo de histórico contendo todos os comandos e dados que você inseriu na linha de comando. Isso pode conter dados confidenciais, incluindo senhas. Por exemplo, se você usar o `ConvertTo-SecureString` cmdlet, a senha será registrada no arquivo de histórico como texto sem formatação. Os arquivos de histórico são um arquivo chamado `$($host.Name)_history.txt` . Em sistemas Windows, o arquivo de histórico é armazenado em `$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine` . Em sistemas não Windows, os arquivos de histórico são armazenados em `$env:XDG_DATA_HOME/powershell/PSReadLine` ou `$env:HOME/.local/share/powershell/PSReadLine` .

### <a name="feedback--contributing-to-psreadline"></a>Comentários & CONTRIBUIndo para o PSReadLine

[PSReadLine no GitHub](https://github.com/PowerShell/PSReadLine)

Sinta-se à vontade para enviar uma solicitação de pull ou enviar comentários na página do GitHub.

## <a name="see-also"></a>CONSULTE TAMBÉM

O PSReadLine é bastante influenciado pela biblioteca do GNU [ReadLine](https://tiswww.case.edu/php/chet/readline/rltop.html) .
