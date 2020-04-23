---
ms.date: 09/06/2019
keywords: powershell, cmdlet
title: Novidades no ISE do PowerShell 5.0
ms.openlocfilehash: 8f15e99c5a6ae33aeae9bd33eb0cf58fb27e3b90
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "74416638"
---
# <a name="whats-new-in-the-windows-powershell-50-ise"></a>Novidades no ISE do Windows PowerShell 5.0

Este tópico explica os recursos novos e atualizados introduzidos na versão 5.0 do ISE (Ambiente de Script Integrado) do Windows PowerShell.

> [!NOTE]
> O ISE do PowerShell não está mais no desenvolvimento ativo de recursos. Como componente de remessa do Windows, ele continua com suporte oficial para correções de segurança e serviços de alta prioridade.
> No momento, não há planos de remover o ISE do Windows.
>
> Não há suporte para o ISE no PowerShell v6 e posteriores. Os usuários que buscam substituir o ISE devem usar o [Visual Studio Code](https://code.visualstudio.com/) com o [PowerShell Extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell).

## <a name="feature-description"></a>Descrição do recurso

O ISE do Windows PowerShell é um aplicativo host que permite gravar, executar e testar scripts e módulos em um ambiente gráfico e intuitivo. Recursos importantes como coloração de sintaxe, preenchimento de guias, depuração visual, conformidade com Unicode e Ajuda contextual permitem uma experiência avançada de script.

Para obter mais informações, confira [Apresentamos o ISE do Windows PowerShell](../components/ise/Introducing-the-Windows-PowerShell-ISE.md).

A tabela a seguir lista os recursos novos e alterados para esta versão do ISE do Windows PowerShell no Windows PowerShell.

## <a name="intellisense"></a>IntelliSense

> Adicionado no ISE 3.0

O IntelliSense é um recurso de assistência de preenchimento automático que faz parte do ISE do Windows PowerShell.
O IntelliSense exibe menus clicáveis dos cmdlets, parâmetros, valores de parâmetro, arquivos ou pastas potencialmente correspondentes conforme você digita.

**Qual é o valor adicionado por esta alteração?**

Com a adição do IntelliSense, é mais fácil descobrir cmdlets e sintaxes ao usar o ISE do Windows PowerShell para criar scripts. Você também pode usar o ISE do Windows PowerShell para conhecer o Windows PowerShell enquanto cria novos scripts.

**O que passou a funcionar de maneira diferente?**

Quando você digita cmdlets no ISE do Windows PowerShell, é exibido um menu de rolagem clicável que permite navegar e selecionar os comandos apropriados.

## <a name="snippets"></a>Snippets

> Adicionado no ISE 3.0

*Snippets de código* são sessões de código Windows PowerShell curtas que você pode inserir nos scritps que cria no ISE do Windows PowerShell. O ISE do Windows PowerShell vem com um conjunto padrão de snippets. Você pode adicionar snippets usando o cmdlet `New-Snippet` enquanto trabalha no ISE do Windows PowerShell.

**Qual é o valor adicionado por esta alteração?**

Usando snippets, você pode montar e criar scripts para automatizar seu ambiente rapidamente.

**O que passou a funcionar de maneira diferente?**

Para usar snippets no Windows PowerShell 3.0 ou posterior, no menu **Editar**, clique em **Iniciar Snippets** ou pressione <kbd>Ctrl</kbd>+<kbd>J</kbd>.

## <a name="add-on-tools"></a>Ferramentas complementares

> Adicionado no PowerShell 3.0

Agora o ISE do Windows PowerShell dá suporte a ferramentas complementares usando o modelo de objeto. Esses complementos são controles do WPF (Windows Presentation Foundation), exibidos como um painel vertical ou horizontal no console. Várias ferramentas complementares em um painel são exibidas como um controle com guias. Você também pode adicionar ou remover ferramentas complementares produzidas por terceiros. Para obter mais informações, confira [Objetivo do modelo de objeto de script do ISE do Windows PowerShell](../components/ise/object-model/Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md).

**Qual é o valor adicionado por esta alteração?**

Os complementos permitem estender e personalizar o ISE do Windows PowerShell com ferramentas que adicionam funcionalidades e podem melhorar sua experiência com scripts.

**O que passou a funcionar de maneira diferente?**

O ISE do Windows PowerShell 3.0 e posterior vêm com o complemento **Comandos**. O complemento **Comandos** permite que você procure cmdlets e acesse a Ajuda para os cmdlets lado a lado com os Painéis de **Script** e **Console**.

Complementos adicionais podem ser encontrados usando o comando **Abrir o Site de Ferramentas Complementares** no menu **Complementos**.

## <a name="restart-manager-and-auto-save"></a>Gerenciador de Reinicialização e Salvamento Automático

> Adicionado no PowerShell 3.0

O ISE do Windows PowerShell agora salva automaticamente os scripts abertos a cada dois minutos em uma localização separada. Quando o ISE do Windows PowerShell é reiniciado após uma falha inesperada ou uma reinicialização, ele recupera os scripts que estavam abertos na última sessão, mesmo que os scripts não tenham sido salvos.

Para alterar o intervalo de salvamento automático, execute o seguinte comando no painel de console: `$psise.Options.AutoSaveMinuteInterval`.

**Qual é o valor adicionado por esta alteração?**

Agora você pode trabalhar no ISE do Windows PowerShell sabendo que os scripts abertos são salvos automaticamente.

**O que passou a funcionar de maneira diferente?**

O ISE do Windows PowerShell 2.0 não salva automaticamente os scripts.

## <a name="most-recently-used-list"></a>Lista de recém-usados

> Adicionado no PowerShell 3.0

O ISE do Windows PowerShell agora tem uma lista de arquivos recém-usados. Quando você abre um arquivo no ISE do Windows PowerShell, ele é adicionado à lista de recém-usados no menu **Arquivo**.

Para alterar o número padrão de arquivos na lista de recém-usados, execute o seguinte comando no Painel de Console: `$psise.Options.MruCount`.

**Qual é o valor adicionado por esta alteração?**

Agora você pode usar a lista de recém-usados para acessar facilmente os arquivos mais usados.

**O que passou a funcionar de maneira diferente?**

O ISE do Windows PowerShell 2.0 não tem uma lista arquivos usados recentemente.

## <a name="console-pane"></a>Painel de Console

> Adicionado no PowerShell 3.0

Os Painéis de Comando e Saída separados que estavam disponíveis na primeira versão do ISE do Windows PowerShell foram combinados em um Painel de Console único. O Painel do Console é semelhante, em termos de função e aparência, a um console típico do Windows PowerShell, mas inclui os aprimoramentos a seguir:

- Cores de sintaxe para texto de entrada (não para texto de saída), incluindo sintaxe XML
- IntelliSense
- Correspondência de chaves
- Indicação de erros
- Suporte total a Unicode
- Ajuda contextual com <kbd>F1</kbd>
- Show-Command contextual com <kbd>Ctrl</kbd>+<kbd>F1</kbd>
- Suporte a scripts complexos e leitura da direita para a esquerda
- Suporte a fontes
- Zoom
- Modos de seleção de linha e seleção de blocos
- Preservação do conteúdo digitado na linha de comando quando você pressiona a <kbd>Seta para cima</kbd> para exibir o histórico no console

**Qual é o valor adicionado por esta alteração?**

A adição dessas alterações do Painel de Console fornece uma experiência de script que é mais consistente com a interface do console.

**O que passou a funcionar de maneira diferente?**

O ISE do Windows PowerShell 2.0 tem Painéis de Comando e de Saída separados.

## <a name="command-line-switches"></a>Opções de linha de comando

> Adicionado no PowerShell 3.0

Se você iniciar o ISE do Windows PowerShell com a linha de comando (digitando **powershell_ise.exe**), será possível adicionar as novas opções de linha de comando a seguir.

- `-NoProfile`: inicia o ISE do Windows PowerShell sem executar `$profile`
- `-Help`: exibe uma janela Ajuda
- `-mta`: inicia o ISE do Windows PowerShell no modo Multi-Threaded Apartment. O modo de operação padrão do ISE do Windows PowerShell é o modo Single-Threaded Apartment ou `-sta`.

**Qual é o valor adicionado por esta alteração?**

A adição dessas opções de linha de comando permite controlar o ambiente no qual o ISE do Windows PowerShell é executado.

**O que passou a funcionar de maneira diferente?**

O ISE do Windows PowerShell 2.0 não reconhece essas opções de linha de comando.

## <a name="new-editor-features"></a>Novos recursos do editor

> Adicionado no PowerShell 3.0

Outros recursos de edição do ISE do Windows PowerShell incluem:

- **Cores de sintaxe de XML** – Agora o ISE do Windows PowerShell tem sintaxe XML colorida da mesma maneira que a sintaxe colorida do Windows PowerShell.
- **Correspondência de chaves** – O ISE do Windows PowerShell inclui o realce e a correspondência de chaves e pode ser usado das seguintes maneiras: (por exemplo, o uso do comando **Ir para Correspondência** ou <kbd>Ctrl</kbd>+<kbd>]</kbd> localizará a chave de fechamento, se você tiver selecionado uma chave de abertura).
- **Exibição de estrutura de tópicos** O Painel de Script dá suporte à exibição das estruturas de tópicos, que permitem recolher ou expandir seções de códigos com cliques nos sinais de adição ou subtração na margem esquerda. Você pode usar chaves ou as marcas `#region` e `#endregion` para marcar o início ou o final de uma seção recolhível. Para expandir ou recolher todas as regiões, pressione <kbd>Ctrl</kbd>+<kbd>M</kbd>.
- **Edição de texto com arrastar e soltar** – O ISE do Windows PowerShell agora dá suporte à edição de texto ao arrastar e soltar. Você pode selecionar qualquer bloco de texto e arrastar o texto para outro local no editor ou no console para mover o texto. Se você mantiver a tecla <kbd>Ctrl</kbd> pressionada enquanto arrasta o texto selecionado, quando soltar o botão do mouse, o texto será copiado para o novo local. Nesta versão do ISE do Windows PowerShell, quando você arrasta e solta arquivos no ISE do Windows PowerShell, ele abre o arquivo.
- **Analisar a exibição de erro** – Erros de análise são indicados com um sublinhado vermelho. Quando você passa o cursor sobre um erro indicado, o texto da dica de ferramenta exibe o problema encontrado no código.
- **Zoom** – É possível definir o percentual de zoom do conteúdo do console usando o Controle Deslizante de Zoom (no canto inferior direito da janela do ISE do Windows PowerShell) ou digitando o comando `$psise.options.Zoom` no Painel de Console.
- **Copiar e colar rich text** – A cópia para a área de transferência no ISE do Windows PowerShell preserva as informações de fonte, tamanho e cor da seleção original.
- **Seleção de bloco** – Você pode selecionar um bloco de texto mantendo a tecla <kbd>ALT</kbd> pressionada enquanto seleciona o texto no Painel de Script com o mouse ou pressionando <kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>Seta</kbd>.

**Qual é o valor adicionado por esta alteração?**

Os recursos de edição adicionais fornecem um ambiente de edição mais consistente e eficiente.

**O que passou a funcionar de maneira diferente?**

Esses aprimoramentos na edição não estavam presentes no ISE do Windows PowerShell 2.0.

## <a name="new-help-viewer-window"></a>Janela do novo visualizador da ajuda

> Adicionado no PowerShell 3.0

Se você pressionar <kbd>F1</kbd> quando o cursor estiver em um cmdlet ou se parte de um cmdlet estiver realçada, o novo visualizador da Ajuda abrirá uma ajuda contextual sobre o cmdlet realçado. Para exibir a ajuda **Sobre** do Windows PowerShell, digite `operators` no painel de console e pressione <kbd>F1</kbd>.

Antes de usar este recurso, baixe a versão mais atual dos tópicos de ajuda do Windows PowerShell do site da Microsoft. O método mais simples para baixar os tópicos da Ajuda é executar o cmdlet `Update-Help` no painel de console durante a execução do ISE do Windows PowerShell como administrador.

Você pode alterar onde a tecla <kbd>F1</kbd> busca Ajuda. No menu **Ferramentas**/**Opções**, na guia **Configurações Gerais** em **Outras Configurações**, você pode marcar ou desmarcar a caixa de seleção **Usar conteúdo da ajuda local em vez de conteúdo online**. Quando marcada, o cliente procurará o cmdlet Help na Ajuda baixada que se encontra na pasta de módulos. Se a caixa de seleção for desmarcada, o cliente procurará na ajuda online.

**Qual é o valor adicionado por esta alteração?**

A ajuda contextual sem deixar seu cmdlet ou script atual fornece uma experiência integrada de aprendizado.

**O que passou a funcionar de maneira diferente?**

Pressionar <kbd>F1</kbd> em versões anteriores do ISE do Windows PowerShell abria o arquivo de ajuda no computador local. No ISE do Windows PowerShell 3.0 e posterior, é aberta uma janela que contém a ajuda para o cmdlet que é configurável e pesquisável. Essa experiência da ajuda é uma novidade no ISE do Windows PowerShell 3.0 e a Ajuda Atualizável é uma novidade no Windows PowerShell 3.0.

## <a name="show-command-cmdlet"></a>Cmdlet Show-Command

> Adicionado no PowerShell 3.0

O cmdlet `Show-Command` permite compor ou executar um cmdlet ou uma função com o preenchimento de um formulário gráfico. O formulário permite que os usuários trabalhem com o Windows PowerShell em um ambiente gráfico.
`Show-Command` também permite que os desenvolvedores de scripts avançados criem rapidamente uma GUI baseada no Windows PowerShell.

**Qual é o valor adicionado por esta alteração?**

Usando `Show-Command` em seus scripts do Windows PowerShell, é possível fornecer aos usuários o ambiente gráfico com o qual eles estão familiarizados. `Show-Command` também pode ajudar os usuários iniciantes a aprender o Windows PowerShell.

**O que passou a funcionar de maneira diferente?**

`Show-Command` é o novo ISE do Windows PowerShell 3.0.

## <a name="see-also"></a>Confira também

Para obter mais informações sobre como usar o ISE do Windows PowerShell, confira [Explorar o Ambiente de Script Integrado do Windows PowerShell](../components/ise/exploring-the-windows-powershell-ise.md).
