---
title: Editar artigos de referência
description: Este artigo explica os requisitos específicos para edição de referências de cmdlet e os tópicos Sobre na documentação do PowerShell.
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: e135f6cc81ba7537a535a08421e1ca9b2b2af573
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81624764"
---
# <a name="editing-reference-articles"></a>Editar artigos de referência

Os artigos de referência de cmdlet têm uma estrutura específica. Ela é definida por [PlatyPS][].
O PlatyPS gera a ajuda de cmdlets para os módulos do PowerShell no Markdown. Depois de editar os arquivos Markdown, o PlatyPS é usado para criar os arquivos de ajuda do MAML usados pelo cmdlet `Get-Help`.

O PlatyPS tem um esquema embutido em código para a referência de cmdlet que é gravado no código. O documento [platyPS.schema.md][] tenta descrever essa estrutura. As violações de esquema causam erros de build que precisam ser corrigidos antes que possamos aceitar sua contribuição.

## <a name="general-guidelines"></a>Diretrizes gerais

- Não remova nenhuma das estruturas de cabeçalho. O PlatyPS espera um conjunto específico de cabeçalhos.
- Os cabeçalhos **Tipo de entrada** e **Tipo de saída** precisam ter um tipo. Se o cmdlet não usar uma entrada nem retornar um valor, use o valor `None`.
- Os blocos de código isolados são permitidos somente na seção [Exemplos](#structuring-examples).
- As extensões de código embutido podem ser usadas em qualquer parágrafo.

## <a name="formatting-about_-files"></a>Formatar arquivos About_

Os arquivos `About_*` são escritos em Markdown, mas são enviados como arquivos de texto sem formatação. Usamos [Pandoc][] para converter a redução em texto sem formatação. Os arquivos `About_*` são formatados para oferecer a melhor compatibilidade com todas as versões do PowerShell e com as ferramentas de publicação.

Diretrizes básicas de formatação:

- Limite as linhas a 80 caracteres. O Pandoc recua alguns blocos de redução, portanto, esses blocos devem ser ajustados.
  - Os blocos de código são limitados a 76 caracteres
  - As tabelas são limitadas a 76 caracteres
  - Os blocos de citações (e alertas) são limitados a 78 caracteres

- Usar os metacaracteres especiais de Pandoc `\`, `$` e `<`
  - Em um cabeçalho – esses caracteres devem ter escape usando um caractere `\` inicial ou colocados em intervalos de código usando aspas invertidas (`` ` ``)
  - Em um parágrafo – esses caracteres devem ser colocados em extensões de código. Por exemplo:

    ~~~markdown
    ### The purpose of the \$foo variable

    The `$foo` variable is used to store ...
    ~~~

- As tabelas precisam se ajustar a 76 caracteres
  - Quebre manualmente o conteúdo das células em várias linhas
  - Use caracteres de abertura e fechamento `|` em cada linha
  - O exemplo a seguir ilustra como construir corretamente uma tabela contendo informações com quebra de linha em várias linhas dentro de uma célula.

    ~~~markdown
    ```
    |Operator|Description                |Example                          |
    |--------|---------------------------|---------------------------------|
    |`-is`   |Returns TRUE when the input|`(get-date) -is [DateTime]`      |
    |        |is an instance of the      |`True`                           |
    |        |specified .NET type.       |                                 |
    |`-isNot`|Returns TRUE when the input|`(get-date) -isNot [DateTime]`   |
    |        |not an instance of the     |`False`                          |
    |        |specified.NET type.        |                                 |
    |`-as`   |Converts the input to the  |`"5/7/07" -as [DateTime]`        |
    |        |specified .NET type.       |`Monday, May 7, 2007 12:00:00 AM`|
    ```
    ~~~

    > [!NOTE]
    > A limitação de 76 colunas aplica-se apenas aos tópicos `About_*`. Você pode usar colunas largas em artigos conceituais ou de referência de cmdlet.

## <a name="structuring-examples"></a>Estruturar exemplos

No esquema do PlatyPS, o cabeçalho **EXAMPLES** é um cabeçalho H2, e cada exemplo é um cabeçalho H3.

Em um exemplo, o esquema não permite que os blocos de código sejam separados por parágrafos. O esquema válido é:

```
### Example #X title

0 or more paragraphs
1 or more code blocks
0 or more paragraphs.
```

Enumere cada exemplo e adicione um breve título.

Por exemplo:

### <a name="example-1-get-cmdlets-functions-and-aliases"></a>Exemplo 1: obter cmdlets, funções e aliases

Esse comando obtém os cmdlets, funções e aliases do PowerShell instalados no computador.

```powershell
Get-Command
```

### <a name="example-2-get-commands-in-the-current-session"></a>Exemplo 2: obter comandos na sessão atual

```powershell
Get-Command -ListImported
```

## <a name="next-steps"></a>Próximas etapas

[Lista de verificação editorial](editorial-checklist.md)

<!-- link references -->
[PlatyPS]: https://github.com/powershell/platyps
[platyPS.schema.md]: https://github.com/PowerShell/platyPS/blob/master/platyPS.schema.md
[issue1806]: https://github.com/MicrosoftDocs/PowerShell-Docs/issues/1806
[about-example]: /PowerShell/module/Microsoft.PowerShell.Core/About/about_Comparison_Operators
[Pandoc]: https://pandoc.org
