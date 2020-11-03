---
description: Descreve os recursos e os requisitos de sistema do Ambiente de Script Integrado do Windows PowerShell (ISE).
keywords: powershell, cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_windows_powershell_ise?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Windows_PowerShell_ISE
ms.openlocfilehash: ec99dec9ea5012b41c10a56a688b23a6fa2c9dd8
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "93196126"
---
# <a name="about-windows-powershell-ise"></a>Sobre ISE do Windows PowerShell

## <a name="short-description"></a>DESCRIÇÃO BREVE

Descreve os recursos e os requisitos de sistema do Ambiente de Script Integrado do Windows PowerShell (ISE).

## <a name="long-description"></a>DESCRIÇÃO LONGA

ISE do Windows PowerShell é um aplicativo de host gráfico para o Windows PowerShell.
No ISE do Windows PowerShell, você pode executar comandos e gravar, testar e depurar scripts em uma única interface gráfica do usuário baseada no Windows. Seus recursos incluem IntelliSense, edição de várias linhas, preenchimento com Tab, salvamento automático, coloração de sintaxe, execução seletiva, ajuda contextual, comando show (comandos de composição em uma janela) e suporte para conjuntos de caracteres de dois bytes e idiomas da direita para a esquerda.

ISE do Windows PowerShell é uma excelente ferramenta para iniciantes. A guia Mostrar janela Comando e novo PowerShell remoto guia você pelas tarefas para que você possa ter êxito na primeira tentativa. Trechos de código e indicadores de erro ajudam você a aprender a linguagem do Windows PowerShell enquanto trabalha.

Os usuários avançados podem aproveitar os recursos sofisticados de depuração, Complementos e o modelo de objeto ISE do Windows PowerShell.

O que há de novo no ISE do Windows PowerShell no Windows PowerShell 4,0

ISE do Windows PowerShell apresenta dois novos recursos no Windows PowerShell 4,0.

- O ISE do Windows PowerShell agora dá suporte à depuração de fluxo de trabalho do Windows PowerShell e à depuração de script remoto. Para obter mais informações, consulte about_Debuggers.

- Foi adicionado suporte ao IntelliSense para as configurações e provedores de Configuração de Estado Desejado do Windows PowerShell.

## <a name="starting-windows-powershell-ise"></a>Iniciando ISE do Windows PowerShell

O ISE do Windows PowerShell está instalado, habilitado e pronto para uso em todas as versões com suporte do Windows.

- Em Windows 8.1, Windows 8, Windows Server 2012 R2 e Windows Server 2012, na tela iniciar, digite PowerShell_ISE e, em seguida, clique em PowerShell_ISE ou ISE do Windows PowerShell.

- No Windows Server 2012 R2 e no Windows Server 2012, no Gerenciador do Servidor, no menu ferramentas, clique em ISE do Windows PowerShell.

- Em versões anteriores do Windows, clique em Iniciar, todos os programas, acessórios, Windows PowerShell e, em seguida, clique em ISE do Windows PowerShell.

- Em um console do Windows PowerShell, Cmd.exe, ou a caixa de execução ou pesquisa no Windows, digite "PowerShell_ise.exe". Você também pode usar os parâmetros de linha de comando, incluindo a opção NoProfile. Para obter mais informações, consulte [PowerShell_ISE.exe console Help](about_powershell_ise_exe.md).

## <a name="running-interactive-commands"></a>Executando comandos interativos

Você pode executar qualquer comando ou expressão do Windows PowerShell no ISE do Windows PowerShell. Você pode usar cmdlets, provedores, snap-ins e módulos como você os usaria no console do Windows PowerShell.

Você pode digitar ou colar comandos interativos no painel de console. Para executar os comandos, você pode usar botões, itens de menu e atalhos de teclado.

Você pode usar o recurso de edição multilinha para digitar ou colar várias linhas de código no painel de console de uma vez. Quando você pressiona a tecla de seta para cima para recuperar o comando anterior, todas as linhas no comando são rechamadas. Ao digitar comandos, pressione SHIFT + ENTER para fazer com que uma nova linha em branco apareça na linha atual.

## <a name="viewing-output"></a>Exibindo saída

Os resultados de comandos e scripts são exibidos no painel de console. Você pode mover ou copiar os resultados do painel de console usando atalhos de teclado ou o botão Copiar na barra de ferramentas, e pode colar os resultados no painel de script ou nos painéis de console ou em outros programas. Para limpar o painel de console, clique no botão "limpar painel de saída" ou digite um dos seguintes comandos:

```
Clear-Host
cls
```

## <a name="writing-scripts-and-functions"></a>Gravando scripts e funções

No painel de script, você pode abrir, compor, editar e executar scripts. O painel de script permite que você edite scripts usando botões e atalhos de teclado. Você também pode copiar, recortar e colar o texto entre o painel de script e o painel de console.

Você pode usar o recurso de execução seletiva para executar todo ou parte de um script. Para executar parte de um script, selecione o texto que você deseja executar e, em seguida, clique no botão Executar seleção ou pressione F8. Por padrão, F8 executa a linha atual.

Os recursos de edição avançada incluem correspondência de chaves, expandir e recolher, números de linha, indicadores de erro, edição de bloco e recuo, cópia rica e conversão de maiúsculas e minúsculas.

## <a name="getting-help"></a>Obtendo ajuda

ISE do Windows PowerShell inclui tópicos de ajuda que descrevem seu uso. Além disso, todos os arquivos de ajuda instalados podem ser acessados nos painéis de script e de comando.

ISE do Windows PowerShell também dá suporte à ajuda contextual. Para obter ajuda sobre um determinado cmdlet, provedor ou palavra-chave, coloque o cursor no nome do item e pressione F1. Para pesquisar os tópicos da ajuda, pressione F1 e digite o termo de pesquisa.

Para atualizar os tópicos da ajuda no computador, use o item de ajuda atualizar o Windows PowerShell no menu ajuda. Este item atualiza a ajuda para os módulos na sessão atual na cultura da interface do usuário atual. É equivalente a executar o cmdlet Update-Help sem parâmetros. Para atualizar a ajuda para os cmdlets que acompanham o Windows PowerShell, inicie ISE do Windows PowerShell com a opção "executar como administrador".

Você também pode usar os cmdlets Get-Help, Save-Help e Update-Help no ISE do Windows PowerShell, exatamente como você o usa no console do Windows PowerShell. No entanto, no ISE do Windows PowerShell, a função Help exibe o tópico inteiro da ajuda, não uma página por vez.

## <a name="debugging-scripts"></a>Depuração de scripts

Você pode usar o depurador de ISE do Windows PowerShell para depurar um script ou uma função do Windows PowerShell. Ao depurar um script, você pode usar itens de menu e teclas de atalho para executar muitas das mesmas tarefas que você executaria no console do Windows PowerShell. Por exemplo, para definir um ponto de interrupção de linha em um script, clique com o botão direito do mouse na linha de código e clique em alternar ponto de interrupção.

À medida que você percorre um script durante a depuração, o realçador de depuração mostra precisamente qual parte do comando está sendo executada e abre automaticamente os arquivos que incluem o chamado de funções e scripts.

Por padrão, o item de menu alternar ponto de interrupção define um ponto de interrupção em uma linha inteira em um script, mas você pode definir um ponto de interrupção em um nome de variável ou de comando.
Você também pode definir um ponto de interrupção em um comando por número de linha e coluna, facilitando a depuração de comandos de pipeline longos.

Geralmente, você pode depurar erros de sintaxe em um script apenas abrindo o arquivo de script em ISE do Windows PowerShell. Os indicadores de erro identificam erros de sintaxe e os recursos de estrutura de tópicos permitem que você recolha partes do script para se concentrar em pontos problemáticos.

Você também pode usar os cmdlets do depurador do Windows PowerShell no painel de comando da mesma forma como você os usaria no console do.

## <a name="running-remote-commands"></a>Executando comandos remotos

O novo recurso de guia remoto do PowerShell facilita a tarefa de estabelecer uma sessão persistente gerenciada pelo usuário do Windows PowerShell ("PSSession") para o computador local ou um computador remoto. O comando abre uma janela pop-up que solicita um nome de computador e a conta de usuário que tem permissão para executar comandos no computador remoto.

## <a name="customizing-the-view"></a>Personalizando a exibição

Você pode usar ISE do Windows PowerShell recursos para mover e redimensionar o painel de console e o painel de script. Você pode mostrar e ocultar qualquer um dos painéis e pode alterar o tamanho do texto em todos os painéis.

Você também pode usar a janela Opções para personalizar a aparência e a operação do ISE do Windows PowerShell. Além disso, ISE do Windows PowerShell tem uma variável de host personalizada, $psISE, que você pode usar para personalizar ISE do Windows PowerShell, incluindo a adição de menus e itens de menu.

## <a name="windows-powershell-ise-profile"></a>Perfil de ISE do Windows PowerShell

ISE do Windows PowerShell tem seu próprio perfil do Windows PowerShell, Microsoft.PowerShellISE_profile.ps1. Nesse perfil, você pode armazenar funções, aliases, variáveis e comandos que você usa em ISE do Windows PowerShell.

Os itens nos perfis de host do Windows PowerShell (CurrentUser de \\ todos os hosts e AllUsers \\ ) também estão disponíveis no ISE do Windows PowerShell, assim como estão em qualquer programa host do Windows PowerShell. No entanto, os itens em seus perfis de console do Windows PowerShell não estão disponíveis no ISE do Windows PowerShell.

As instruções para mover e reconfigurar seus perfis estão disponíveis na ajuda do ISE do Windows PowerShell e no about_Profiles.

## <a name="notes"></a>OBSERVAÇÕES

ISE do Windows PowerShell é um recurso opcional do Windows ativado por padrão nas versões de cliente e servidor do Windows. Para habilitar e desabilitar ISE do Windows PowerShell em versões de cliente do Windows, use ativar ou desativar recursos do Windows no painel de controle. Para habilitar e desabilitar ISE do Windows PowerShell em versões de servidor do Windows, use o assistente para adicionar funções e recursos no Gerenciador do Servidor.

Como ISE do Windows PowerShell requer uma interface do usuário, ela não funciona em instalações Server Core do Windows Server. No entanto, se você adicionar o recurso ISE do Windows PowerShell, a instalação será automaticamente convertida em servidor com uma GUI.

O ISE do Windows PowerShell é compilado no WPF (Windows Presentation Foundation).
Se os elementos gráficos de ISE do Windows PowerShell não forem renderizados corretamente no sistema, você poderá resolver o problema adicionando ou ajustando as configurações de renderização de gráficos "Desabilitar aceleração de hardware do WPF" em seu sistema. Para obter mais informações, consulte [configurações do registro de renderização de gráficos](/dotnet/framework/wpf/graphics-multimedia/graphics-rendering-registry-settings) na biblioteca MSDN.

## <a name="see-also"></a>CONSULTE TAMBÉM

[about_Debuggers](about_Debuggers.md)

[about_Profiles](about_Profiles.md)

[about_Updatable_Help](about_Updatable_Help.md)

[Get-Help](xref:Microsoft.PowerShell.Core.Get-Help)

[Get-IseSnippet](xref:ISE.Get-IseSnippet)

[Import-IseSnippet](xref:ISE.Import-IseSnippet)

[New-IseSnippet](xref:ISE.New-IseSnippet)

[Save-Help](xref:Microsoft.PowerShell.Core.Save-Help)

[Show-Command](xref:Microsoft.PowerShell.Utility.Show-Command)

[Update-Help](xref:Microsoft.PowerShell.Core.Update-Help)
