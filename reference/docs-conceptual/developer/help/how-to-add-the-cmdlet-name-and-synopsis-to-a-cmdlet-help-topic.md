---
ms.date: 09/13/2016
ms.topic: reference
title: Como adicionar a sinopse e o nome do cmdlet a um tópico de ajuda do cmdlet
description: Como adicionar a sinopse e o nome do cmdlet a um tópico de ajuda do cmdlet
ms.openlocfilehash: aeeb0cdd1d6d17b88067928ff952dc57a9441917
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659051"
---
# <a name="how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic"></a>Como adicionar a sinopse e o nome do cmdlet a um tópico de ajuda do cmdlet

Esta seção descreve como adicionar conteúdo exibido nas seções **nome** e **Sinopse** da ajuda do cmdlet. No arquivo de ajuda, esse conteúdo é adicionado ao nó de comando para cada cmdlet.

> [!NOTE]
> Para obter uma exibição completa de um arquivo de ajuda, abra um dos `dll-Help.xml` arquivos localizados no diretório de instalação do PowerShell. Por exemplo, o `Microsoft.PowerShell.Commands.Management.dll-Help.xml` arquivo contém conteúdo para vários cmdlets do PowerShell.

## <a name="to-add-the-cmdlet-name-and-a-synopsis"></a>Para adicionar o nome do cmdlet e uma sinopse

- A ajuda do cmdlet pode exibir duas descrições para o cmdlet. A primeira descrição é uma breve descrição que é conhecida como Sinopse. A segunda descrição é uma descrição mais detalhada que é abordada na [adição da descrição detalhada a um tópico de ajuda de cmdlet](./how-to-add-a-cmdlet-description.md).
  Ambas as descrições devem ser escritas como um único parágrafo.

- Na Sinopse, não repita o nome do cmdlet. Informar ao usuário que o `Get-Server` cmdlet obtém um servidor é breve, mas não é informativo. Em vez disso, use sinônimos e adicione detalhes à descrição.

  Exemplo: "Obtém um objeto que representa um computador local ou remoto".

- Use verbos simples, como "Get", "Create" e "Change" na Sinopse. Evite usar "set" porque ele é vago e palavras sofisticadas, como "Modify".

  Exemplo: "Obtém informações sobre a assinatura Authenticode em um arquivo".

- Gravar no Active Voice. Por exemplo, "usar o objeto TimeSpan..." é muito mais claro do que "o objeto TimeSpan pode ser usado para..."

- Evite o verbo "display" ao descrever os cmdlets que obtêm objetos. Embora o Windows PowerShell exiba dados de cmdlet, é importante introduzir os usuários ao conceito que o cmdlet retorna .NET Framework objetos cujos dados podem não ser exibidos. Se você enfatizar a exibição, o usuário pode não perceber que o cmdlet pode ter retornado muitas outras propriedades e métodos úteis que não são exibidos.

## <a name="see-also"></a>Consulte Também

[SDK do Windows PowerShell](../windows-powershell-reference.md)
