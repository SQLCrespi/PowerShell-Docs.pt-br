---
title: Gravando ajuda para cmdlets do PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55908d67-7cbe-482a-a105-5a6da93c5311
caps.latest.revision: 4
ms.openlocfilehash: fd565e8bf8429d91d785664c8cc69d1843439219
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560586"
---
# <a name="writing-help-for-powershell-cmdlets"></a>Gravando ajuda para cmdlets do PowerShell

Os cmdlets do PowerShell podem ser úteis, mas a menos que os tópicos da ajuda expliquem claramente o que o cmdlet faz e como usá-lo, o cmdlet pode não ser usado ou, ainda pior, pode frustrar os usuários.
O formato de arquivo de ajuda do cmdlet baseado em XML aprimora a consistência, mas a grande ajuda requer muito mais.

Se você nunca escreveu a ajuda do cmdlet, examine as diretrizes a seguir.
O esquema XML necessário para criar o tópico de ajuda do cmdlet é descrito na seção a seguir.
Comece com [a criação do arquivo de ajuda do cmdlet](./how-to-create-the-cmdlet-help-file.md).
Esse tópico inclui uma descrição dos nós XML de nível superior.

## <a name="writing-guidelines-for-cmdlet-help"></a>Diretrizes de escrita para a ajuda do cmdlet

### <a name="write-well"></a>Gravar bem
Nada substitui um tópico bem escrito.
Se você não for um escritor profissional, encontre um gravador ou editor para ajudá-lo.
Outra alternativa é copiar o texto de ajuda para o Microsoft Word e usar as verificações gramaticais e ortográficas para melhorar seu trabalho.

### <a name="write-simply"></a>Escrever simplesmente
Use palavras e frases simples.
Evite jargões.
Considere que muitos leitores estão equipados apenas com um dicionário de idioma estrangeiro e o tópico da ajuda.

### <a name="write-consistently"></a>Escreva de forma consistente
A ajuda para os cmdlets relacionados deve ser semelhante (por exemplo, Get-x e Set-x).
Use as descrições padrão para parâmetros padrão, como **Force** e **InputObject**.
(Copie-os da ajuda para os cmdlets principais.) Use os termos padrão.
Por exemplo, use "Parameter", não "Argument" e use "cmdlet", não "Command" ou "command-let".

### <a name="start-the-synopsis-with-a-verb"></a>Iniciar o resumo com um verbo
O campo Sinopse informa ao usuário o que o cmdlet faz, não o que é ou como ele funciona.
Os verbos criam uma instrução baseada em tarefa que informa os usuários se esse cmdlet atende aos seus requisitos.
Use verbos simples, como "Get", "Create" e "Change".
Evite "set", que podem ser palavras vagas e sofisticadas como "Modify".

### <a name="focus-on-objects"></a>Foco em objetos
A maioria dos cmdlets de "Get" exibe algo, mas sua função principal é obter um objeto.
Em sua ajuda, concentre-se no objeto, para que os usuários entendam que a exibição padrão é uma das muitas e que eles podem usar os métodos e as propriedades do objeto que você recuperou para eles de maneiras diferentes.

### <a name="write-detailed-descriptions"></a>Escrever descrições detalhadas
Liste rapidamente tudo o que o cmdlet pode fazer na descrição detalhada.
Se a função main for alterar uma propriedade, mas o cmdlet puder alterar todas as propriedades, liste-a na descrição detalhada.

### <a name="use-conventional-syntax"></a>Usar sintaxe convencional
Use o formato padrão Backus-Naur, que é comum para a ajuda de linha de comando do UNIX e do Windows.

### <a name="use-microsoft-net-framework-types-for-parameter-values"></a>Usar tipos de estrutura de Microsoft .NET para valores de parâmetro
Os espaços reservados para valores de parâmetro (nas descrições de sintaxe e parâmetro) mostram os tipos de .NET Framework dos objetos que o parâmetro aceitará.
A equipe do PowerShell desenvolveu essa Convenção para ajudar a ensinar os usuários sobre o .NET Framework.

### <a name="write-complete-parameter-descriptions"></a>Gravar descrições de parâmetros completas
As descrições de parâmetro devem informar os usuários de duas coisas: o que o parâmetro faz (seu efeito) e o que eles devem digitar para os valores de parâmetro.

### <a name="write-practical-examples"></a>Escrever exemplos práticos
Os exemplos devem mostrar como usar todos os parâmetros, mas a coisa mais importante é mostrar como usar o cmdlet em tarefas do mundo real.
Comece com um exemplo simples e escreva exemplos cada vez mais complexos.
No exemplo final, mostre como usar o cmdlet em um pipeline.

### <a name="use-the-notes-field"></a>Usar o campo observações
Use o campo observações para explicar os conceitos que os usuários precisam para entender o cmdlet.
Você também pode usar observações para ajudar os usuários a evitar erros comuns.
Evite URLs à medida que elas forem alteradas.
Em vez disso, forneça aos usuários os termos para pesquisar.

### <a name="test-your-help"></a>Teste sua ajuda
Teste a ajuda exatamente como você testa seu código.
Faça com que amigos e colegas leiam o conteúdo da ajuda e forneçam comentários.
Você também pode solicitar comentários de grupos de notícias.

## <a name="see-also"></a>Consulte Também

 [Como criar o arquivo de ajuda do cmdlet](./how-to-create-the-cmdlet-help-file.md)

 [Como adicionar a sinopse e o nome do cmdlet a um tópico de ajuda do cmdlet](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)

 [Como adicionar a descrição detalhada a um tópico de ajuda de cmdlet](./how-to-add-a-cmdlet-description.md)

 [Como adicionar sintaxe a um tópico de ajuda do cmdlet](./how-to-add-syntax-to-a-cmdlet-help-topic.md)

 [Como adicionar parâmetros a um tópico de ajuda de cmdlet](./how-to-add-parameter-information.md)

 [Como adicionar tipos de entrada a um tópico de ajuda de cmdlet](./how-to-add-input-types-to-a-cmdlet-help-topic.md)

 [Como adicionar valores retornados a um tópico de ajuda do cmdlet](./how-to-add-return-values-to-a-cmdlet-help-topic.md)

 [Como adicionar notas a um tópico de ajuda do cmdlet](./how-to-add-notes-to-a-cmdlet-help-topic.md)

 [Como adicionar exemplos a um tópico de ajuda do cmdlet](./how-to-add-examples-to-a-cmdlet-help-topic.md)

 [Como adicionar links relacionados a um tópico de ajuda do cmdlet](./how-to-add-related-links-to-a-cmdlet-help-topic.md)

 [SDK do Windows PowerShell](../windows-powershell-reference.md)
