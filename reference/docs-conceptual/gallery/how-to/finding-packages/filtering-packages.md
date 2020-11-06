---
ms.date: 06/12/2017
title: Filtrando resultados da pesquisa
description: Este artigo descreve a interface do usuário usada para filtrar conteúdo na Galeria do PowerShell.
ms.openlocfilehash: cc375f3ddb35c95ed134776500bd326bc3db6b1a
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92661407"
---
# <a name="filtering-search-results"></a>Filtrando resultados da pesquisa

A [guia Pacotes](https://www.powershellgallery.com/packages) exibe todos os pacotes disponíveis na Galeria do PowerShell.

Há várias maneiras de filtrar, classificar e pesquisar os pacotes. Para ver mais detalhes sobre um pacote específico, clique nele.

## <a name="filter-by"></a>Filtrar Por

O menu suspenso em "Filtrar Por" permite aos usuários filtrar os resultados por:

- Incluir pré-lançamento
- Apenas estável

Para saber mais sobre itens de "pré-lançamento" e "estáveis", confira o artigo [Prerelease Versioning Added to PowerShellGet and PowerShell Gallery](https://blogs.msdn.microsoft.com/powershell/2017/12/05/prerelease-versioning-added-to-powershellget-and-powershell-gallery/) (Controle de versão de pré-lançamento adicionado ao PowerShellGet e à Galeria do PowerShell), no blog da equipe do PowerShell.

Com as caixas de seleção no menu suspenso, os usuários podem filtrar os resultados por:

- Tipos de Pacote
  - Módulo
  - Script
- Categorias
  - Cmdlet
  - Recurso de DSC
  - Função
  - Capacidade da função
  - Fluxo de trabalho

Para ver somente módulos na Galeria do PowerShell, marque a opção Módulo nos Tipos de Pacote. Da mesma forma, para ver somente scripts na Galeria do PowerShell, marque a opção Script nos Tipos de Pacote.

> [!NOTE]
> Os filtros são inclusivos. Exemplo: um pacote que contém cmdlets e funções será exibido se Cmdlet ou Função (ou ambos) estiverem marcados. Se nenhum dos dois for selecionado, o pacote não será exibido. De forma semelhante, se todas as categorias forem selecionadas, apenas pacotes que contêm uma dessas categorias serão exibidos. **Pacotes que não pertencem a nenhuma dessas categorias não serão exibidos.**

## <a name="sort-by"></a>Classificar Por

O menu suspenso Classificar Por permite aos usuários classificar os resultados por:

- Popularidade – a popularidade é determinada pela Contagem de Downloads
- A a Z – em ordem alfabética por nome do pacote
- Recentes – os pacotes aparecem na ordem da data de publicação

## <a name="search-box"></a>Caixa de Pesquisa

A Caixa de Pesquisa permite que os usuários pesquisem pacotes por palavras-chave.
Para saber mais, confira [Sintaxe de Pesquisa da Galeria](search-syntax.md).
