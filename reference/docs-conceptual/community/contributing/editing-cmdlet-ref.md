---
title: Editar artigos de referência
description: Este artigo explica os requisitos específicos para edição de referências de cmdlet e os tópicos Sobre na documentação do PowerShell.
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: 3c6f1b4fc27ca8ece7ec30317daf4ed2a6bc9228
ms.sourcegitcommit: 18d832858a7b8ea094763afa753e0f48f01372e7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/10/2020
ms.locfileid: "79060321"
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

Os arquivos `About_*` agora são processados pelo [Pandoc][], em vez do PlatyPS. Os arquivos `About_*` são formatados para oferecer a melhor compatibilidade com todas as versões do PowerShell e com as ferramentas de publicação.

Diretrizes básicas de formatação:

- Limite as linhas a 80 caracteres
- Os blocos de código e as tabelas são limitados a 76 caracteres, pois o Pandoc os recua em quatro espaços durante a conversão para texto sem formatação
- As tabelas precisam se ajustar a 76 caracteres
  - Quebre manualmente o conteúdo das células em várias linhas
  - Use caracteres de abertura e fechamento `|` em cada linha
  - Confira um exemplo funcional em [about_Comparison_Operators][about-example]
- Use os caracteres especiais do Pandoc `\`, `$` e `<`
  - Em um cabeçalho – esses caracteres devem ter escape usando um caractere `\` inicial ou entre aspas invertidas (`` ` ``)
  - Em um parágrafo – esses caracteres devem ser colocados em extensões de código. Por exemplo:

    ~~~markdown
    ### The purpose of the \$foo variable

    The `$foo` variable is used to store ...
    ~~~

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
[about-example]: https://github.com/MicrosoftDocs/PowerShell-Docs/reference/5.1/Microsoft.PowerShell.Core/About/about_Comparison_Operators.md
[Pandoc]: https://pandoc.org
