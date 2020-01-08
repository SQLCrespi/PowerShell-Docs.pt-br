---
ms.date: 08/14/2018
keywords: powershell, cmdlet
title: Apresentando o Windows PowerShell ISE
ms.openlocfilehash: 3e4471d0982ba4d7ef1a9d59906a9ff297f6f7cb
ms.sourcegitcommit: 058a6e86eac1b27ca57a11687019df98709ed709
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "75736157"
---
# <a name="the-windows-powershell-ise"></a>O ISE do Windows PowerShell

O ISE (Ambiente de Script Integrado) do Windows PowerShell é um aplicativo host do Windows PowerShell. No ISE, você pode executar comandos e escrever, testar e depurar scripts em uma interface gráfica de usuário única baseada no Windows. A ISE fornece edição em várias linhas, preenchimento com tabulação, coloração de sintaxe, execução seletiva, ajuda contextual e suporte para idiomas da direita para esquerda. Itens de menu e atalhos de teclado são mapeados para executar muitas das mesmas tarefas que você executaria no console do Windows PowerShell. Por exemplo, quando você depura um script no ISE, é possível clicar com botão direito do mouse em uma linha de código no painel de edição para definir um ponto de interrupção.

## <a name="support"></a>Suporte

O ISE foi introduzido pela primeira vez com o Windows PowerShell V2 e foi reformulado com o PowerShell V3. Há suporte para o ISE em todas as versões compatíveis do Windows PowerShell até e incluindo a versão do Windows PowerShell v 5.1.

> [!NOTE]
> O ISE do PowerShell não está mais no desenvolvimento ativo de recursos. Como componente de remessa do Windows, ele continua com suporte oficial para correções de segurança e serviços de alta prioridade.
> No momento, não há planos de remover o ISE do Windows.
>
> Não há suporte para o ISE no PowerShell v6 e posteriores. Os usuários que buscam substituir o ISE devem usar o [Visual Studio Code](https://code.visualstudio.com/) com o [PowerShell Extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell).

## <a name="key-features"></a>Principais recursos

Novos recursos no ISE do Windows PowerShell:

- Edição em várias linhas: Para inserir uma linha em branco abaixo da linha atual no painel Comando, pressione <kbd>Shift</kbd>+<kbd>Enter</kbd>.
- Execução seletiva: Para executar parte de um script, selecione o texto que você deseja executar e clique no botão **Executar Script**. Ou pressione <kbd>F5</kbd>.
- Ajuda contextual: Digite `Invoke-Item` e pressione <kbd>F1</kbd>. O arquivo da Ajuda é aberto no artigo para o cmdlet `Invoke-Item`.

O ISE do Windows PowerShell permite personalizar alguns aspectos de sua aparência. Ele também tem seu próprio script de perfil do Windows PowerShell.

## <a name="to-start-the-windows-powershell-ise"></a>Para iniciar o Windows PowerShell ISE

Clique em **Iniciar**, selecione **Windows PowerShell** e clique em **ISE do Windows PowerShell**.
Como alternativa, você pode digitar `powershell_ise.exe` em qualquer shell de comando ou na caixa Executar.

## <a name="to-get-help-in-the-windows-powershell-ise"></a>Para obter ajuda no Windows PowerShell ISE

No menu **Ajuda**, clique em **Ajuda do Windows PowerShell**. Ou pressione <kbd>F1</kbd>. O arquivo aberto descreve o ISE do Windows PowerShell e o Windows PowerShell, inclusive toda a ajuda disponível no cmdlet `Get-Help`.
