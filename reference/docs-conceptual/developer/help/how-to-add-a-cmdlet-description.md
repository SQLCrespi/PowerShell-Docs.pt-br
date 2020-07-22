---
title: Como adicionar uma descrição do cmdlet
ms.date: 09/13/2016
ms.openlocfilehash: 2b98c4cefc3a55eccfeb7eba5a290e7d93a6088b
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893230"
---
# <a name="how-to-add-a-cmdlet-description"></a>Como adicionar uma descrição do cmdlet

Esta seção descreve como adicionar conteúdo exibido na seção **Descrição** da ajuda do cmdlet. No arquivo de ajuda, esse conteúdo é adicionado ao nó de **comando** para cada cmdlet.

> [!NOTE]
> Para obter uma exibição completa de um arquivo de ajuda, abra um dos `dll-Help.xml` arquivos localizados no diretório de instalação do PowerShell. Por exemplo, o `Microsoft.PowerShell.Commands.Management.dll-Help.xml` arquivo contém conteúdo para vários cmdlets do PowerShell.

### <a name="to-add-a-description"></a>Para adicionar uma descrição

- Comece explicando os recursos básicos do cmdlet em mais detalhes. Em muitos casos, você pode explicar os termos usados no nome do cmdlet e ilustrar conceitos desconhecidos com um exemplo. Por exemplo, se o cmdlet acrescentar dados a um arquivo, explique que ele adiciona dados ao final de um arquivo existente.

- Para localizar todos os recursos do cmdlet, examine a lista de parâmetros. Descreva a função principal do cmdlet e, em seguida, inclua outras funções e recursos. Por exemplo, se a função main do cmdlet for alterar uma propriedade, mas o cmdlet puder alterar todas as propriedades, digamos que na descrição detalhada. Se os parâmetros do cmdlet permitirem que os usuários solicitem informações de maneiras diferentes, explique isso.

- Inclua informações sobre as maneiras como os usuários podem usar o cmdlet, além dos usos óbvios. Por exemplo, você pode usar o objeto que o `Get-Host` cmdlet recupera para alterar a cor do texto na janela de comando do Windows PowerShell.

  Exemplo: "o `Get-Acl` cmdlet obtém objetos que representam o descritor de segurança de um arquivo ou recurso. O descritor de segurança contém as listas de controle de acesso (ACLs) do recurso. A ACL especifica as permissões que os usuários e grupos de usuários têm para acessar o recurso. "

- A descrição detalhada deve descrever o cmdlet, mas não deve descrever os conceitos que o cmdlet usa. Coloque as definições de conceito em observações adicionais.

## <a name="see-also"></a>Consulte Também

[SDK do Windows PowerShell](../windows-powershell-reference.md)
