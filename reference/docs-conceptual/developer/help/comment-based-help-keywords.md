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
ms.openlocfilehash: 3c5736be7066a749744482cb79edad2f53705f07
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83564117"
---
# <a name="comment-based-help-keywords"></a>Palavras-chave de ajuda baseada em comentários

Este tópico lista e descreve as palavras-chave na Ajuda baseada em comentários.

## <a name="keywords-in-comment-based-help"></a>Palavras-chave na Ajuda baseada em comentários

Veja a seguir as palavras-chave de ajuda com base em comentários válidas. Eles são listados na ordem em que normalmente aparecem em um tópico da ajuda junto com o uso pretendido. Essas palavras-chave podem aparecer em qualquer ordem na Ajuda baseada em comentários e não diferenciam maiúsculas de minúsculas.

Observe que a `.ExternalHelp` palavra-chave tem precedência sobre todas as outras palavras-chaves de ajuda baseadas em comentários. Quando `.ExternalHelp` o estiver presente, o cmdlet [Microsoft. PowerShell. Commands. GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) não exibirá ajuda baseada em comentários, mesmo quando ele não encontrar um arquivo de ajuda que corresponda ao valor da palavra-chave.

`.Synopsis`Uma breve descrição da função ou do script. Essa palavra-chave pode ser usada apenas uma vez em cada tópico.

`.Description`Uma descrição detalhada da função ou do script. Essa palavra-chave pode ser usada apenas uma vez em cada tópico.

`.Parameter`* \< Nome do parâmetro>* a descrição de um parâmetro. Você pode incluir uma `.Parameter` palavra-chave para cada parâmetro na função ou script.

As `.Parameter` palavras-chave podem aparecer em qualquer ordem no bloco de comentários, mas a ordem na qual os parâmetros aparecem na `Param` instrução ou declaração de função determina a ordem na qual os parâmetros aparecem no tópico da ajuda. Para alterar a ordem dos parâmetros no tópico da ajuda, altere a ordem dos parâmetros na `Param` instrução ou na declaração da função.

Você também pode especificar uma descrição de parâmetro colocando um comentário na `Param` instrução imediatamente antes do nome da variável de parâmetro. Se você usar um `Param` Comentário de instrução e uma `.Parameter` palavra-chave, a descrição associada à `.Parameter` palavra-chave será usada e o `Param` Comentário da instrução será ignorado.

`.Example`Um comando de exemplo que usa a função ou o script, opcionalmente seguido por saída de exemplo e uma descrição. Repita essa palavra-chave para cada exemplo.

`.Inputs`Os tipos de Microsoft .NET Framework de objetos que podem ser canalizados para a função ou o script. Você também pode incluir uma descrição dos objetos de entrada.

`.Outputs`O tipo de .NET Framework dos objetos que o cmdlet retorna. Você também pode incluir uma descrição dos objetos retornados.

`.Notes`Informações adicionais sobre a função ou o script.

`.Link`O nome de um tópico relacionado. Repita essa palavra-chave para cada tópico relacionado. Esse conteúdo aparece na seção links relacionados do tópico da ajuda.

O `.Link` conteúdo da palavra-chave também pode incluir um URI (Uniform Resource Identifier) em uma versão online do mesmo tópico da ajuda. A versão online é aberta quando você usa o `Online` parâmetro de Get-Help. O URI deve começar com "http" ou "https".

`.Component`A tecnologia ou o recurso que a função ou o script usa, ou ao qual ele está relacionado. Esse conteúdo é exibido quando o comando Get-Help inclui o `Component` parâmetro de Get-Help.

`.Role`A função de usuário para o tópico da ajuda. Esse conteúdo é exibido quando o comando Get-Help inclui o `Role` parâmetro de Get-Help.

`.Functionality`O uso pretendido da função. Esse conteúdo é exibido quando o comando Get-Help inclui o `Functionality` parâmetro de Get-Help.

`.ForwardHelpTargetName``<Command-Name>`Redireciona para o tópico da ajuda para o comando especificado. Você pode redirecionar os usuários para qualquer tópico da ajuda, incluindo tópicos de ajuda para uma função, script, cmdlet ou provedor.

`.ForwardHelpCategory``<Category>`Especifica a categoria de ajuda do item em ForwardHelpTargetName. Os valores válidos são alias, cmdlet, ArquivoDeAjuda, função, provedor, geral, perguntas frequentes, Glossário, ScriptCommand, ExternalScript, filtro ou todos. Use essa palavra-chave para evitar conflitos quando houver comandos com o mesmo nome.

`.RemoteHelpRunspace``<PSSession-variable>`Especifica uma sessão que contém o tópico da ajuda. Insira uma variável que contenha uma PSSession. Essa palavra-chave é usada pelo `Export-PSSession` cmdlet para localizar os tópicos da ajuda para os comandos exportados.

`.ExternalHelp``<XML Help File>`Especifica o caminho e/ou o nome de um arquivo de ajuda baseado em XML para o script ou função.

A `.ExternalHelp` palavra-chave informa ao cmdlet [Microsoft. PowerShell. Commands. GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) para obter ajuda para o script ou a função em um arquivo baseado em XML. O **. **A palavra-chave ExternalHelp é necessária ao usar um arquivo de ajuda baseado em XML para um script ou uma função. Sem ele, `Get-Help` o não encontrará um arquivo de ajuda para a função ou o script.

A `.ExternalHelp` palavra-chave tem precedência sobre todas as outras palavras-chaves de ajuda baseadas em comentários. Quando `.ExternalHelp` o estiver presente, o cmdlet [Microsoft. PowerShell. Commands. GetHelpCommand](/dotnet/api/Microsoft.PowerShell.Commands.gethelpcommand) não exibirá ajuda baseada em comentários, mesmo quando ele não encontrar um arquivo de ajuda que corresponda ao valor da palavra-chave.

Quando a função é exportada por um módulo de script, o valor de `.ExternalHelp` deve ser um nome de arquivo sem um caminho. `Get-Help`procura o arquivo em um subdiretório específico da localidade do diretório do módulo. Não há requisitos para o nome do arquivo, mas uma prática recomendada é usar o seguinte formato de nome de arquivo: `<ScriptModule>.psm1-help.xml` .

Quando a função não estiver associada a um módulo, inclua um caminho e um nome de arquivo no valor de **. **Palavra-chave ExternalHelp. Se o caminho especificado para o arquivo XML contiver subdiretórios específicos da cultura da interface do usuário, `Get-Help` o pesquisará os subdiretórios recursivamente para um arquivo XML com o nome do script ou da função de acordo com os padrões de fallback de idioma estabelecidos para o Windows, assim como faz para todos os tópicos de ajuda baseados em XML.

Para obter mais informações sobre o formato de arquivo de ajuda baseado em XML da ajuda do cmdlet, consulte [a ajuda do cmdlet Writing Windows PowerShell](./writing-help-for-windows-powershell-cmdlets.md).
