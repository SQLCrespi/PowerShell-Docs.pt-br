---
title: Lista de verificação editorial
description: Esta é uma lista resumida de regras para editar a documentação do PowerShell.
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: b5baf7366239084779d34e23f218e5e6222ed1a3
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81624730"
---
# <a name="editors-checklist"></a>Lista de verificação do editor

Este é um resumo das regras a serem aplicadas ao escrever novos artigos ou atualizar existentes. Confira outros artigos no Guia do colaborador para obter explicações detalhadas e exemplos dessas regras.

## <a name="metadata"></a>Metadados

- `ms.date`: deve estar no formato **MM/DD/AAAA**
  - Alterar a data em que houver uma atualização significativa ou real
    - Reorganizar o artigo
    - Corrigir erros reais
    - Adicionar novas informações
  - Não altere a data se a atualização não for significativa
    - Corrigir erros de digitação e formatação
- `title`: sequência única de 43 a 59 caracteres, incluindo espaços
  - Não inclua o identificador do site (ele é gerado automaticamente)
  - Use maiúsculas e minúsculas - coloque em maiúscula apenas a primeira palavra e quaisquer nomes próprios
- `description`: 115-145 caracteres incluindo espaços - esse resumo é exibido no resultado da pesquisa

## <a name="formatting"></a>Formatação

- Elementos de sintaxe de backtick que aparecem, embutidos, dentro de um parágrafo
  - Nomes dos cmdlets `Verb-Noun`
  - Variável `$counter`
  - Exemplos sintáticos `Verb-Noun -Parameter`
  - Caminhos de arquivo `C:\Program Files\PowerShell`, `/usr/bin/pwsh`
  - URLs que não devem ser clicáveis no documento
  - Valores de propriedade ou parâmetro
- Use negrito para nomes de: propriedade, parâmetros, classes, módulos, entidades, objetos ou tipos
  - Negrito é usado para marcação semântica, não para ênfase
  - Negrito - use asteriscos `**`
- Itálico - use sublinhado `_`
  - Usado apenas para ênfase, não para marcação semântica
- Quebras de linha em 100 colunas (ou em 80 para **about_Topics**)
- Sem guias rígidas - use somente espaços
- Sem espaços à direita nas linhas

### <a name="headers"></a>headers

- H1 é o primeiro - apenas um H1 por artigo
- Use apenas [Cabeçalhos ATX](https://github.github.com/gfm/#atx-headings)
- Use maiúsculas e minúsculas para todos os cabeçalhos
- Não pule os níveis - sem H3 sem H2
- Profundidade máxima do H3 ou H4
- Linha em branco antes e depois
- O PlatyPS aplica cabeçalhos específicos em seu esquema - não adicione ou remova cabeçalhos

### <a name="code-blocks"></a>Blocos de código

- Linha em branco antes e depois
- Usar limites de código marcados -  **powershell**, **Saída** ou outro ID de linguagem apropriado
- Limite não marcado - blocos de sintaxe ou outros shells
- Coloque a saída em um bloco de código separado, exceto em exemplos simples, nos quais você não pretende que o leitor use o botão **Copiar**
- Confira uma lista de [linguagens com suporte](/contribute/code-in-docs#supported-languages)

### <a name="lists"></a>Listas

- Recuado corretamente
- Linha em branco antes do primeiro item e após o último item
- Marcador - uso de hífen (`-`) não asterisco (`*` )- muito fácil de confundir com ênfase
- Para listas numeradas, todos os números são "1".

## <a name="terminology"></a>Terminologia

- PowerShell vs. Windows PowerShell vs. PowerShell Core
- Confira a [Terminologia do Produto](powershell-style-guide.md#product-terminology)

## <a name="cmdlet-reference-examples"></a>Exemplos de referência de cmdlet

- Deve ter pelo menos um exemplo na referência de cmdlet
- Os exemplos devem ser apenas o código suficiente para demonstrar o uso
- Sintaxe do PowerShell
  - Usar nomes completos de cmdlets e parâmetros - sem aliases
  - Use nivelamento para parâmetros quando a linha de comando ficar muito longa
  - Evite usar backticks de continuação de linha - use somente quando necessário
- Remova ou simplifique o prompt do PowerShell (`PS>`), exceto quando necessário para o exemplo
- O exemplo de referência de cmdlet deve seguir o seguinte esquema do PlatyPS

  ~~~Markdown
  ### Example 1 - Descriptive title

  Zero or more short descriptive paragraphs explaining the context of the example followed by one or
  more code blocks. Recommend at least one and no more than two.

  ```powershell
  ... one or more PowerShell code statements ...
  ```

  ```Output
  Example output of the code above.
  ```

  Zero or more optional follow up paragraphs that explain the details of the code and output.
  ~~~

- Não insira parágrafos entre os blocos de código. Todo o conteúdo descritivo deve vir antes ou depois dos blocos de código.

## <a name="linking-to-other-documents"></a>Vinculação a outros documentos

- Vinculação fora do docset ou entre conceitos e referência de cmdlet
  - Use URLs relativas ao vincular ao docs.microsoft.com (remova `https://docs.microsoft.com/en-us`)
  - Não inclua localidades em URLs nas propriedades da Microsoft (por exemplo, remova `/en-us` da URL)
  - Todas as URLs para sites externos devem usar HTTPS, a menos que isso não seja válido para o site de destino
- No docset
  - Link para o caminho do arquivo (por exemplo, `../folder/file.md`)
  - Todos os caminhos de arquivo usam caracteres de barra (`/`)
- Links de imagem devem ter texto alt exclusivo
