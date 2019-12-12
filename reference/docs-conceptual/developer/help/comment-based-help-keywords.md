---
title: Palavras-chave de ajuda com base em comentários | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab90ec96-77f5-42e3-9c7e-2f4156ec207f
caps.latest.revision: 6
ms.openlocfilehash: 534a6c9a43326c8a01b2181c7a799286fa4d3997
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361355"
---
# <a name="comment-based-help-keywords"></a>Palavras-chave de ajuda baseada em comentários

Este tópico lista e descreve as palavras-chave na Ajuda baseada em comentários.

## <a name="keywords-in-comment-based-help"></a>Palavras-chave na Ajuda baseada em comentários

Veja a seguir as palavras-chave de ajuda com base em comentários válidas. Eles são listados na ordem em que normalmente aparecem em um tópico da ajuda junto com o uso pretendido. Essas palavras-chave podem aparecer em qualquer ordem na Ajuda baseada em comentários e não diferenciam maiúsculas de minúsculas.

Observe que a palavra-chave `.ExternalHelp` tem precedência sobre todas as demais palavras-chave de ajuda com base em comentários. Quando `.ExternalHelp` estiver presente, o cmdlet [Microsoft. PowerShell. Commands. GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) não exibirá ajuda baseada em comentários, mesmo quando ele não encontrar um arquivo de ajuda que corresponda ao valor da palavra-chave.

`.Synopsis` uma breve descrição da função ou do script. Essa palavra-chave pode ser usada apenas uma vez em cada tópico.

`.Description` uma descrição detalhada da função ou do script. Essa palavra-chave pode ser usada apenas uma vez em cada tópico.

`.Parameter` *\<parâmetro-Name >* a descrição de um parâmetro. Você pode incluir uma palavra-chave `.Parameter` para cada parâmetro na função ou script.

As palavras-chave `.Parameter` podem aparecer em qualquer ordem no bloco de comentários, mas a ordem na qual os parâmetros aparecem na instrução `Param` ou na declaração de função determina a ordem na qual os parâmetros aparecem no tópico da ajuda. Para alterar a ordem dos parâmetros no tópico da ajuda, altere a ordem dos parâmetros na instrução `Param` ou na declaração da função.

Você também pode especificar uma descrição de parâmetro colocando um comentário na instrução `Param` imediatamente antes do nome da variável de parâmetro. Se você usar um comentário de instrução `Param` e uma palavra-chave `.Parameter`, a descrição associada à palavra-chave `.Parameter` será usada e o comentário da instrução `Param` será ignorado.

`.Example` um comando de exemplo que usa a função ou o script, opcionalmente seguido por saída de exemplo e uma descrição. Repita essa palavra-chave para cada exemplo.

`.Inputs` os tipos de Microsoft .NET estrutura de objetos que podem ser canalizados para a função ou o script. Você também pode incluir uma descrição dos objetos de entrada.

`.Outputs` o tipo de .NET Framework dos objetos que o cmdlet retorna. Você também pode incluir uma descrição dos objetos retornados.

`.Notes` informações adicionais sobre a função ou o script.

`.Link` o nome de um tópico relacionado. Repita essa palavra-chave para cada tópico relacionado. Esse conteúdo aparece na seção links relacionados do tópico da ajuda.

O conteúdo da palavra-chave `.Link` também pode incluir um URI (Uniform Resource Identifier) em uma versão online do mesmo tópico da ajuda. A versão online é aberta quando você usa o parâmetro `Online` de Get-Help. O URI deve começar com "http" ou "https".

`.Component` a tecnologia ou o recurso que a função ou o script usa, ou ao qual ele está relacionado. Esse conteúdo é exibido quando o comando Get-Help inclui o parâmetro `Component` de Get-Help.

`.Role` a função de usuário para o tópico da ajuda. Esse conteúdo é exibido quando o comando Get-Help inclui o parâmetro `Role` de Get-Help.

`.Functionality` o uso pretendido da função. Esse conteúdo é exibido quando o comando Get-Help inclui o parâmetro `Functionality` de Get-Help.

`.ForwardHelpTargetName` `<Command-Name>` redireciona para o tópico da ajuda para o comando especificado. Você pode redirecionar os usuários para qualquer tópico da ajuda, incluindo tópicos de ajuda para uma função, script, cmdlet ou provedor.

`.ForwardHelpCategory` `<Category>` especifica a categoria de ajuda do item em ForwardHelpTargetName. Os valores válidos são alias, cmdlet, ArquivoDeAjuda, função, provedor, geral, perguntas frequentes, Glossário, ScriptCommand, ExternalScript, filtro ou todos. Use essa palavra-chave para evitar conflitos quando houver comandos com o mesmo nome.

`.RemoteHelpRunspace` `<PSSession-variable>` especifica uma sessão que contém o tópico da ajuda. Insira uma variável que contenha uma PSSession. Essa palavra-chave é usada pelo cmdlet `Export-PSSession` para localizar os tópicos da ajuda para os comandos exportados.

`.ExternalHelp` `<XML Help File>` especifica o caminho e/ou o nome de um arquivo de ajuda baseado em XML para o script ou a função.

A palavra-chave `.ExternalHelp` informa o cmdlet [Microsoft. PowerShell. Commands. GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) para obter ajuda para o script ou a função em um arquivo baseado em XML. O **.** A palavra-chave ExternalHelp é necessária ao usar um arquivo de ajuda baseado em XML para um script ou uma função. Sem ele, `Get-Help` não encontrará um arquivo de ajuda para a função ou o script.

A palavra-chave `.ExternalHelp` tem precedência sobre todas as outras palavras-chave de ajuda com base em comentários. Quando `.ExternalHelp` estiver presente, o cmdlet [Microsoft. PowerShell. Commands. GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) não exibirá ajuda baseada em comentários, mesmo quando ele não encontrar um arquivo de ajuda que corresponda ao valor da palavra-chave.

Quando a função é exportada por um módulo de script, o valor de `.ExternalHelp` deve ser um nome de arquivo sem um caminho. `Get-Help` procura o arquivo em um subdiretório específico da localidade do diretório do módulo. Não há requisitos para o nome do arquivo, mas uma prática recomendada é usar o seguinte formato de nome de arquivo: `<ScriptModule>.psm1-help.xml`.

Quando a função não estiver associada a um módulo, inclua um caminho e um nome de arquivo no valor de **.** Palavra-chave ExternalHelp. Se o caminho especificado para o arquivo XML contiver subdiretórios específicos da cultura da interface do usuário, `Get-Help` pesquisará os subdiretórios recursivamente para um arquivo XML com o nome do script ou função de acordo com os padrões de fallback de idioma estabelecidos para o Windows, assim como faz para todos os tópicos de ajuda baseados em XML.

Para obter mais informações sobre o formato de arquivo de ajuda baseado em XML da ajuda do cmdlet, consulte [a ajuda do cmdlet Writing Windows PowerShell](./writing-help-for-windows-powershell-cmdlets.md).