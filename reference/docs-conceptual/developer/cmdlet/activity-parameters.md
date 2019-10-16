---
title: Parâmetros de atividade | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e4e0cf6-19e0-44b8-8b40-d6f6075276cf
caps.latest.revision: 5
ms.openlocfilehash: 489d8bcdabe904d6a3d2bc6cdb9d7e23d09cbef2
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364635"
---
# <a name="activity-parameters"></a>Parâmetros de atividade

A tabela a seguir lista os nomes recomendados e a funcionalidade para parâmetros de atividade.

|Parâmetro|Funcionalidade|
|---|---|
|**Anexar**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que o usuário possa adicionar conteúdo ao final de um recurso quando o parâmetro for especificado.|
|**CaseSensitive**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que o usuário possa exigir a diferenciação de maiúsculas e minúsculas quando o parâmetro for especificado.|
|**Linha**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar uma cadeia de caracteres de comando a ser executada.|
|**CompatibleVersion**<br>Tipo de dados: objeto System. Version|Implemente esse parâmetro para que o usuário possa especificar a semântica com a qual o cmdlet deve ser compatível para compatibilidade com as versões anteriores.|
|**Compactar**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que a compactação de dados seja usada quando o parâmetro for especificado.|
|**Compactar**<br>Tipo de dados: palavra-chave|Implemente esse parâmetro para que o usuário possa especificar o algoritmo a ser usado para compactação de dados.|
|**Visa**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que os dados sejam processados até que o usuário encerre o cmdlet quando o parâmetro for especificado. Se o parâmetro não for especificado, o cmdlet processará uma quantidade predefinida de dados e encerrará a operação.|
|**Criada**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para indicar que um recurso será criado se ainda não existir um quando o parâmetro for especificado.|
|**Apagar**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que os recursos sejam excluídos quando o cmdlet tiver concluído sua operação quando o parâmetro for especificado.|
|**Desperdício**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para indicar que os itens de trabalho pendentes são processados antes que o cmdlet processe novos dados quando o parâmetro é especificado. Se o parâmetro não for especificado, os itens de trabalho serão processados imediatamente.|
|**Borracha**<br>Tipo de dados: Int32|Implemente esse parâmetro para que o usuário possa especificar o número de vezes que um recurso é apagado antes de ser excluído.|
|**ErrorLevel**<br>Tipo de dados: Int32|Implemente esse parâmetro para que o usuário possa especificar o nível de erros a serem relatados.|
|**Excluí**<br>Tipo de dados: String []|Implemente esse parâmetro para que o usuário possa excluir algo de uma atividade. Para obter mais informações sobre como usar filtros de entrada, consulte [parâmetros de filtro de entrada](input-filter-parameters.md).|
|**Sem**<br>Tipo de dados: palavra-chave|Implemente esse parâmetro para que o usuário possa especificar um filtro que selecione os recursos sobre os quais executará a ação do cmdlet. Para obter mais informações sobre como usar filtros de entrada, consulte [parâmetros de filtro de entrada](./input-filter-parameters.md).|
|**Dar**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que o progresso seja rastreado quando o parâmetro for especificado.|
|**Aplicação**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para indicar que o usuário pode executar uma ação, mesmo que as restrições sejam encontradas quando o parâmetro for especificado. O parâmetro não permite que a segurança seja comprometida. Por exemplo, esse parâmetro permite que um usuário substitua um arquivo somente leitura.|
|**Incluir**<br>Tipo de dados: String []|Implemente esse parâmetro para que o usuário possa incluir algo em uma atividade. Para obter mais informações sobre como usar filtros de entrada, consulte [parâmetros de filtro de entrada](input-filter-parameters.md).|
|**Lucrativ**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para indicar que o processamento é executado incrementalmente quando o parâmetro é especificado. Por exemplo, esse parâmetro permite que um usuário execute backups incrementais que fazem backup de arquivos somente desde o último backup.|
|**InputObject**<br>Tipo de dados: objeto|Implemente esse parâmetro quando o cmdlet usar a entrada de outros cmdlets. Quando você define um parâmetro **InputObject** , sempre especifique a palavra-chave **ValueFromPipeline** ao declarar o atributo de **parâmetro** . Para obter mais informações sobre como usar filtros de entrada, consulte [parâmetros de filtro de entrada](./input-filter-parameters.md).|
|**Inserido**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que o cmdlet Insira um item quando o parâmetro for especificado.|
|**Interactive**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que o cmdlet funcione interativamente com o usuário quando o parâmetro for especificado.|
|**Intervalo**<br>Tipo de dados: HashTable|Implemente esse parâmetro para que o usuário possa especificar uma tabela de hash de palavras-chave que contenham os valores. O exemplo a seguir mostra valores de exemplo para o parâmetro **Interval** : `-interval @{ResumeScan=15; Retry=3}`.|
|**Log**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro auditar as ações do cmdlet quando o parâmetro for especificado.|
|**NoClobber**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que o recurso não seja substituído quando o parâmetro for especificado. Esse parâmetro geralmente se aplica a cmdlets que criam novos objetos para que eles possam ser impedidos de substituir objetos existentes com o mesmo nome.|
|**Sobre**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que o usuário seja notificado de que a atividade será concluída quando o parâmetro for especificado.|
|**NotifyAddress**<br>Tipo de dados: endereço de email|Implemente esse parâmetro para que o usuário possa especificar o endereço de email a ser usado para enviar uma notificação quando o parâmetro **Notify** for especificado.|
|**Gravado**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que o cmdlet Substitua todos os dados existentes quando o parâmetro for especificado.|
|**Aviso**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar um prompt para o cmdlet.|
|**Tranqüilo**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que o cmdlet suprime os comentários do usuário durante suas ações quando o parâmetro é especificado.|
|**Recurse**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que o cmdlet execute recursivamente suas ações em recursos quando o parâmetro for especificado.|
|**Corrige**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que o cmdlet tente corrigir algo de um estado desfeito quando o parâmetro for especificado.|
|**Repairstring**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar uma cadeia de caracteres a ser usada quando o parâmetro de **reparo** for especificado.|
|**Repita**<br>Tipo de dados: Int32|Implemente esse parâmetro para que o usuário possa especificar o número de vezes que o cmdlet tentará realizar uma ação.|
|**Não**<br>Tipo de dados: matriz de palavras-chave|Implemente esse parâmetro para que o usuário possa especificar uma matriz dos tipos de itens.|
|**Fluxo**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que o usuário possa transmitir vários objetos de saída por meio do pipeline quando o parâmetro for especificado.|
|**Strict**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que todos os erros sejam tratados como erros de encerramento quando o parâmetro for especificado.|
|**TempLocation**<br>Tipo de dados: cadeia de caracteres|Implemente esse parâmetro para que o usuário possa especificar o local dos dados temporários que são usados durante a operação do cmdlet.|
|**Cedido**<br>Tipo de dados: Int32|Implemente esse parâmetro para que o usuário possa especificar o intervalo de tempo limite (em milissegundos).|
|**Truncar**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que o cmdlet truncará suas ações quando o parâmetro for especificado. Se o parâmetro não for especificado, o cmdlet executará outra ação.|
|**Confirme**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que o cmdlet seja testado para determinar se uma ação ocorreu quando o parâmetro é especificado.|
|**Esperado**<br>Tipo de dados: SwitchParameter|Implemente esse parâmetro para que o cmdlet aguarde a entrada do usuário antes de continuar quando o parâmetro for especificado.
|**WaitTime**<br>Tipo de dados: Int32|Implemente esse parâmetro para que o usuário possa especificar a duração (em segundos) que o cmdlet aguardará a entrada do usuário quando o parâmetro **Wait** for especificado.|

## <a name="see-also"></a>Consulte Também

[Parâmetros de cmdlet](./cmdlet-parameters.md)

[Writing a Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md) (Escrevendo um Cmdlet do Windows PowerShell)

[SDK do Windows PowerShell](../windows-powershell-reference.md)
