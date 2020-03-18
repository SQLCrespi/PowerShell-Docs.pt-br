---
title: Contribuir para a documentação do PowerShell
description: Este artigo é uma visão geral de como começar como um colaborador da documentação do PowerShell.
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: 5db78ae2805cb26aa79aa698cfb8b5d8ba8911dc
ms.sourcegitcommit: c97dcf1e00ef540e7464c36c88f841474060044c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2020
ms.locfileid: "79402623"
---
# <a name="contributing-to-powershell-documentation"></a>Contribuir para a documentação do PowerShell

Agradecemos pelo seu suporte ao PowerShell!

O Guia do colaborador é uma coleção de artigos que explicam as ferramentas e os processos que usamos para criar a documentação na Microsoft. Alguns desses guias abrangem informações que são comuns a qualquer conjunto de documentação publicado no [docs.microsoft.com][docs]. Alguns dos guias são específicos sobre como escrevemos a documentação do PowerShell.

Os artigos comuns estão disponíveis em nosso [Guia do colaborador][contribute] centralizado. Os guias específicos do PowerShell estão disponíveis aqui.

## <a name="ways-to-contribute"></a>Formas de contribuição

Há duas maneiras de contribuir. Ambas as contribuições são valiosas para nós.

- [Registrar problemas][file-an-issue] nos ajuda a identificar problemas e lacunas em nossa documentação. Às vezes, os problemas são difíceis de resolver, exigindo mais investigação e pesquisa. O processo do problema nos permite ter uma conversa sobre o problema e desenvolver uma resolução satisfatória.

- Enviar novo conteúdo ou alterar artigos existentes é um processo mais complexo. As informações a seguir descrevem as ferramentas, os processos e os padrões para enviar conteúdo à documentação.

## <a name="prepare-to-make-a-contribution"></a>Preparar-se para fazer uma contribuição

Contribuir com a documentação requer uma conta do GitHub. Use a lista de verificação a seguir para obter as ferramentas e entender os processos que usamos para fazer contribuições.

1. [Inscrever-se no GitHub](/contribute/get-started-setup-github)
1. [Instalar ferramentas do Markdown e do Git](/contribute/get-started-setup-tools)
1. [Instalar o Pacote de criação de documentos](/contribute/how-to-write-docs-auth-pack)
1. [Instalar o Posh-Git][posh-git] – não obrigatório, mas recomendado
1. [Configurar um repositório Git local](/contribute/get-started-setup-local)
1. [Revisar os conceitos básicos do Git e do GitHub](/contribute/git-github-fundamentals)

## <a name="get-started-writing-docs"></a>Comece a colaborar para a documentação

Há duas maneiras de contribuir com alterações na documentação:

1. [Edições rápidas em documentos existentes](/contribute/#quick-edits-to-existing-documents)
   - Correções secundárias, correção de erros de digitação ou pequenas adições
1. [Fluxo de trabalho completo do GitHub para documentos](/contribute/how-to-write-workflows-major)
   - grandes alterações, várias versões, adição ou alteração de imagens ou colaboração em novos artigos

Além disso, leia a seção [Fundamentos da escrita](/contribute/style-quick-start) do Guia do colaborador centralizado. Outro recurso excelente é o [Guia de estilo de escrita da Microsoft][style-guide]. O objetivo do Guia de estilo de escrita da Microsoft é ajudar os editores, redatores técnicos, desenvolvedores, profissionais de marketing e qualquer outra pessoa em TI a escrever um conteúdo melhor.

As correções secundárias ou esclarecimentos na documentação e nos exemplos de código em repositórios públicos são cobertos pelos[Termos de Uso][terms-of-use] do docs.microsoft.com.

Use o fluxo de trabalho completo do GitHub quando estiver fazendo alterações significativas. Se você não for um funcionário da Microsoft, as alterações significativas gerarão um comentário na solicitação de pull, pedindo o envio de um [CLA (Contrato de Licença de Contribuição)][cla] online. Precisamos que você preencha o formulário online antes de revisarmos ou aceitarmos sua solicitação de pull.

## <a name="code-of-conduct"></a>Código de conduta

Todos os repositórios que publicam no docs.microsoft.com adotaram o [Código de conduta de software livre da Microsoft](https://opensource.microsoft.com/codeofconduct/) ou o [Código de conduta do .NET Foundation](https://dotnetfoundation.org/code-of-conduct). Para obter mais informações, confira as [Perguntas frequentes sobre o Código de conduta](https://opensource.microsoft.com/codeofconduct/faq/).

## <a name="next-steps"></a>Próximas etapas

Os artigos a seguir abrangem informações específicas da documentação do PowerShell. Quando há sobreposição nas diretrizes do Guia do colaborador centralizado, destacamos como essas regras se diferem para o conteúdo do PowerShell.

Examine os seguintes documentos:

- [Como arquivar um problema](file-an-issue.md)
- [Introdução à escrita de documentos](get-started-writing.md)
- [Enviar uma solicitação de pull](pull-requests.md)
- [Guia de estilo do PowerShell-Docs](powershell-style-guide.md)
- [Editar referência de cmdlet](editing-cmdlet-ref.md)

Recursos adicionais

- [Lista de verificação editorial](editorial-checklist.md)
- [Como gerenciamos problemas](managing-issues.md)
- [Como gerenciamos solicitações de pull](managing-pull-requests.md)

<!--link refs-->
[cla]: https://cla.microsoft.com/
[contribute]: /contribute/
[docs]: https://docs.microsoft.com/
[file-an-issue]: file-an-issue.md
[posh-git]: https://www.powershellgallery.com/packages/posh-git
[psdocs]: https://docs.microsoft.com/powershell
[style-guide]: https://docs.microsoft.com/style-guide/welcome/
[terms-of-use]: https://docs.microsoft.com/legal/termsofuse