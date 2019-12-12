---
title: Referência de XML de esquema de formato | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac6f7aaa-d0cc-4c7b-a341-85e736174579
caps.latest.revision: 21
ms.openlocfilehash: 437b3d6bb62fdd3a74f3392ec71df360c01a1974
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363715"
---
# <a name="format-schema-xml-reference"></a>Referência XML de esquema de formato

Os tópicos nesta seção descrevem os elementos XML usados pela formatação de arquivos (arquivos Format. ps1xml). Arquivos de formatação definem como o objeto .NET é exibido; Eles não alteram o objeto em si.

## <a name="in-this-section"></a>Nesta seção

[Elemento Alignment para TableColumnHeader para TableControl (Format)](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md) Define como os dados em um cabeçalho de coluna são exibidos.

[Elemento Alignment para TableColumnItem para TableControl (Format)](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md) Define como os dados na linha são exibidos.

[Elemento AutoSize para TableControl (Format)](./autosize-element-for-tablecontrol-format.md) Especifica se o tamanho da coluna e o número de colunas são ajustados com base no tamanho dos dados.

[Elemento AutoSize para WideControl (Format)](./autosize-element-for-widecontrol-format.md) Especifica se o tamanho da coluna e o número de colunas são ajustados com base no tamanho dos dados.

[Elemento ColumnNumber para WideControl (Format)](./columnnumber-element-for-widecontrol-format.md) Especifica o número de colunas exibidas na exibição ampla.

[Elemento Configuration (Format)](./configuration-element-format.md) Representa o elemento de nível superior do arquivo de formatação.

[Elemento Control para controles para configuração (Format)](./control-element-for-controls-for-configuration-format.md) Define um controle comum que pode ser usado por todas as exibições do arquivo de formatação e pelo nome usado para fazer referência ao controle.

[Elemento Control para controles para View (Format)](./control-element-for-controls-for-view-format.md) Define um controle que pode ser usado pela exibição e o nome que é usado para referenciar o controle.

[Elemento Controls para configuração (Format)](./controls-element-for-configuration-format.md) Define os controles comuns que podem ser usados por todas as exibições do arquivo de formatação.

[Elemento Controls para View (Format)](./controls-element-for-view-format.md) Define os controles de exibição que podem ser usados por uma exibição específica.

[Elemento CustomControl para controle de configuração (formato)](./customcontrol-element-for-control-for-controls-for-configuration-format.md) Define um controle. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

[Elemento CustomControl para controle de controles para View (Format)](./customcontrol-element-for-control-for-controls-for-view-format.md) Define um controle que é usado pela exibição.

[Elemento CustomControl para GroupBy (Format)](./customcontrol-element-for-groupby-format.md) Define o controle personalizado que exibe o novo grupo.

[Elemento CustomControl (Format)](./customcontrol-element-for-groupby-format.md) Define um formato de controle personalizado para a exibição.

[Elemento CustomControlName para ExpressionBinding para controles para configuração (Format)](./customcontrolname-element-for-expressionbinding-for-controls-for-configuration-format.md) Especifica o nome de um controle comum. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

[Elemento CustomControlName para ExpressionBindine para controles para View (Format)](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md) Especifica o nome de um controle comum ou um controle de exibição. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

[Elemento CustomControlName de GroupBy (Format)](./customcontrolname-element-for-groupby-format.md) Especifica o nome de um controle personalizado que é usado para exibir o novo grupo. Esse elemento é usado ao definir uma tabela, lista, exibição de controle largo ou personalizada.

[Elemento CustomEntry para CustomControl para controles para configuração (Format)](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md) Fornece uma definição do controle comum. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

[Elemento CustomEntry para CustomEntries para controles para View (Format)](./customentry-element-for-customentries-for-controls-for-view-format.md) Fornece uma definição do controle. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

[Elemento CustomEntry para CustomEntries para exibição (formato)](./customentry-element-for-customentries-for-customcontrol-for-view-format.md) Fornece uma definição da exibição de controle personalizado.

[Elemento CustomEntry para CustomControl para GroupBy (Format)](./customentry-element-for-customcontrol-for-groupby-format.md) Fornece uma definição do controle. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

[Elemento CustomEntries para CustomControl para configuração (formato)](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md) Fornece as definições de um controle comum. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

[Elemento CustomEntries para CustomControl para controles para View (Format)](./customentries-element-for-customcontrol-for-controls-for-view-format.md) Fornece as definições para o controle. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

[Elemento CustomEntries para CustomControl para GroupBy (Format)](./customentries-element-for-customcontrol-for-groupby-format.md) Fornece as definições para o controle. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

[Elemento CustomEntries para CustomControl para exibição (formato)](./customentries-element-for-customcontrol-for-view-format.md) Fornece as definições do modo de exibição de controle personalizado. A exibição de controle personalizado deve especificar uma ou mais definições.

[Elemento CustomItem para CustomEntry para controles de configuração](./customitem-element-for-customentry-for-controls-for-configuration-format.md) Define quais dados são exibidos pelo controle e como eles são exibidos. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

[Elemento CustomItem para CustomEntry para controles para View (Format)](./customitem-element-for-customentry-for-controls-for-view-format.md) Define quais dados são exibidos pelo controle e como eles são exibidos. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

[Elemento CustomItem para CustomEntry para exibição (formato)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md) Define quais dados são exibidos pelo modo de exibição de controle personalizado e como eles são exibidos. Esse elemento é usado ao definir um modo de exibição de controle personalizado.

[Elemento CustomItem para CustomEntry para GroupBy (Format)](./customitem-element-for-customentry-for-groupby-format.md) Define quais dados são exibidos pelo modo de exibição de controle personalizado e como eles são exibidos. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

[Elemento DefaultSettings (formato)](./defaultsettings-element-format.md) Define as configurações comuns que se aplicam a todas as exibições do arquivo de formatação. As configurações comuns incluem a exibição de erros, o encapsulamento de texto em tabelas, a definição de como as coleções são expandidas e muito mais.

[Elemento DisplayError (Format)](./displayerror-element-format.md) Especifica que a cadeia de caracteres #ERR é exibida quando ocorre um erro exibindo uma parte dos dados.

[Elemento EntrySelectedBy para CustomEntry para controles para configuração (Format)](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md) Define os tipos .NET que usam a definição do controle comum ou a condição que deve existir para que esse controle seja usado. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

[Elemento EntrySelectedBy para CustomEntry para controles para View (Format)](./entryselectedby-element-for-customentry-for-controls-for-view-format.md) Define os tipos .NET que usam essa definição de controle ou a condição que deve existir para que essa definição seja usada. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

[Elemento EntrySelectedBy para CustomEntry para exibição (formato)](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md) Define os tipos .NET que usam essa entrada personalizada ou a condição que deve existir para que essa entrada seja usada.

[Elemento EntrySelectedBy para EnumerableExpansion (Format)](./entryselectedby-element-for-enumerableexpansion-format.md) Define os tipos .NET que usam essa definição ou a condição que deve existir para que essa definição seja usada.

[Elemento EntrySelectedBy para CustomEntry para GroupBy (Format)](./entryselectedby-element-for-customentry-for-groupby-format.md) Define os tipos .NET que usam essa definição de controle ou a condição que deve existir para que essa definição seja usada. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

[Elemento EntrySelectedBy para ListEntry para ListControl (formato)](./entryselectedby-element-for-listentry-for-listcontrol-format.md) Define os tipos .NET que usam essa definição de exibição de lista ou a condição que deve existir para que essa definição seja usada. Na maioria dos casos, apenas uma definição é necessária para uma exibição de lista. No entanto, você pode fornecer várias definições para o modo de exibição de lista se quiser usar a mesma exibição de lista para exibir dados diferentes para objetos diferentes.

[Elemento EntrySelectedBy para TableRowEntry (Format)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) Define os tipos .NET cujos valores de propriedade são exibidos na linha.

[Elemento EntrySelectedBy para WideEntry (Format)](./entryselectedby-element-for-wideentry-format.md) Define os tipos .NET que usam essa definição da exibição larga ou a condição que deve existir para que essa definição seja usada.

[Elemento EnumerableExpansion (Format)](./enumerableexpansion-element-format.md) Define como os objetos de coleção .NET específicos são expandidos quando são exibidos em uma exibição.

[Elemento EnumerableExpansions (Format)](./enumerableexpansions-element-format.md) Define como os objetos de coleção .NET são expandidos quando são exibidos em uma exibição.

[Elemento enumeracollection para ExpressionBinding para controles para configuração (Format)](./enumeratecollection-element-for-expressionbinding-for-controls-for-configuration-format.md) Especificado que os elementos das coleções são exibidos pelo controle. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

[Elemento enumeracollection para ExpressionBinding para controles para View (Format)](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md) Especificado que os elementos das coleções são exibidos. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

[Elemento enumeracollection para a associação de expressão para CustomControl para exibição (formato)](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md) Especifica que os elementos das coleções são exibidos. Esse elemento é usado ao definir um modo de exibição de controle personalizado.

[Elemento enumeracollection para ExpressionBinding para GroupBy (Format)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md) Especifica que os elementos das coleções são exibidos. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

[Elemento Expand (formato)](./expand-element-format.md) Especifica como o objeto de coleção é expandido para essa definição.

[Elemento ExpressionBinding para CustomItem para controles para configuração (Format)](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md) Define os dados que são exibidos pelo controle. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

[Elemento ExpressionBinding para CustomItem para controles para View (Format)](./expressionbinding-element-for-customitem-for-controls-for-view-format.md) Define os dados que são exibidos pelo controle. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

[Elemento ExpressionBinding para CustomItem para CustomControl para exibição (formato)](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md) Define os dados que são exibidos pelo controle. Esse elemento é usado ao definir um modo de exibição de controle personalizado.

[Elemento ExpressionBinding para CustomItem para GroupBy (Format)](./expressionbinding-element-for-customitem-for-groupby-format.md) Define os dados que são exibidos pelo controle. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

[Elemento FirstLineHanging para frame para controles para configuração (Format)](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) Especifica quantos caracteres a primeira linha de dados é deslocada para a esquerda. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

[Elemento FirstLineHanging do quadro de controles de View (Format)](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) Especifica quantos caracteres a primeira linha de dados é deslocada para a esquerda. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

[Elemento FirstLineHanging para frame para CustomControl para View (Format)](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) Especifica quantos caracteres a primeira linha de dados é deslocada para a esquerda. Esse elemento é usado ao definir um modo de exibição de controle personalizado.

[Elemento FirstLineHanging para frame para GroupBy (Format)](./firstlinehanging-element-for-frame-for-groupby-format.md) Especifica quantos caracteres a primeira linha de dados é deslocada para a esquerda. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

[Elemento FirstLineIndent para frame para controles para configuração (Format)](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) Especifica quantos caracteres a primeira linha de dados é deslocada para a direita. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

[Elemento FirstLineIndent do quadro de controles de View (Format)](./firstlineindent-element-for-frame-for-controls-for-view-format.md) Especifica quantos caracteres a primeira linha de dados é deslocada para a direita. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

[Elemento FirstLineIndent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) Especifica quantos caracteres a primeira linha de dados é deslocada para a direita. Esse elemento é usado ao definir um modo de exibição de controle personalizado.

[Elemento FirstLineIndent para frame para GroupBy (Format)](./firstlineindent-element-for-frame-for-groupby-format.md) Especifica quantos caracteres a primeira linha de dados é deslocada para a direita. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

[Elemento FormatString para ListItem (Format)](./formatstring-element-for-listitem-for-listcontrol-format.md) Especifica um padrão de formato que define como o valor de propriedade ou script é exibido.

[Elemento FormatString para TableColumnItem (Format)](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md) Especifica um padrão de formato que define como o valor de propriedade ou script da tabela é exibido.

[Elemento FormatString para WideItem para WideControl (Format)](./formatstring-element-for-wideitem-for-widecontrol-format.md) Especifica um padrão de formato que define como o valor de propriedade ou script é exibido na exibição.

[Elemento frame para CustomItem para controles para configuração (Format)](./frame-element-for-customitem-for-controls-for-configuration-format.md) Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

[Elemento frame para CustomItem para controles para View (Format)](./frame-element-for-customitem-for-controls-for-view-format.md) Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

[Elemento frame para CustomItem para CustomControl para exibição (formato)](./frame-element-for-customitem-for-customcontrol-for-view-format.md) Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita. Esse elemento é usado ao definir um modo de exibição de controle personalizado.

[Elemento frame para CustomItem para GroupBy (Format)](./frame-element-for-customitem-for-groupby-format.md) Define como os dados são exibidos, como deslocar os dados para a esquerda ou para a direita. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

[Elemento GroupBy para exibição (formato)](./groupby-element-for-view-format.md) Define como o Windows PowerShell exibe um novo grupo de objetos.

[Elemento HideTableHeaders (Format)](./hidetableheaders-element-format.md) Especifica que os cabeçalhos da tabela não são exibidos.

[Elemento ItemSelectionCondition para ExpressionBinding para controles para configuração (Format)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md) Define a condição que deve existir para que esse controle seja usado. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

[Elemento ItemSelectionCondition de ExpressionBinding para controles para View (Format)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md) Define a condição que deve existir para que esse controle seja usado. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

[Elemento ItemSelectionCondition para a associação de expressão para CustomControl para exibição (formato)](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md) Define a condição que deve existir para que esse controle seja usado. Não há nenhum limite para o número de condições de seleção que podem ser especificadas para um item de controle. Esse elemento é usado ao definir um modo de exibição de controle personalizado.

[Elemento ItemSelectionCondition para ExpressionBinding para GroupBy (Format)](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md) Define a condição que deve existir para que esse controle seja usado. Não há nenhum limite para o número de condições de seleção que podem ser especificadas para um item de controle. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

[Elemento ItemSelectionCondition para ListItem (Format)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md) Define a condição que deve existir para este item de lista ser usado.

[Elemento Label para ListItem para ListControl (Format)](./label-element-for-listitem-for-listcontrol-format.md) Especifica o rótulo para a propriedade ou o valor do script na linha.

[Elemento Label para GroupBy (Format)](./label-element-for-groupby-format.md) Especifica um rótulo que é exibido quando um novo grupo é encontrado.

[Elemento Label para TableColumnHeader (Format)](./label-element-for-tablecolumnheader-for-tablecontrol-format.md) Define o rótulo que é exibido na parte superior de uma coluna.

[Elemento LeftIndent para frame para controles para configuração (Format)](./leftindent-element-for-frame-for-controls-for-configuration-format.md) Especifica quantos caracteres os dados são deslocados para fora da margem esquerda. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

[Elemento LeftIndent do quadro de controles de View (Format)](./leftindent-element-for-frame-for-controls-for-view-format.md) Especifica quantos caracteres os dados são deslocados para fora da margem esquerda. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

[Elemento LeftIndent para frame para CustomControl para View (Format)](./leftindent-element-for-frame-for-customcontrol-for-view-format.md) Especifica quantos caracteres os dados são deslocados para fora da margem esquerda. Esse elemento é usado ao definir um modo de exibição de controle personalizado.

[Elemento LeftIndent para frame para GroupBy (Format)](./leftindent-element-for-frame-for-groupby-format.md) Especifica quantos caracteres os dados são deslocados para fora da margem esquerda. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

[Elemento ListControl (formato)](./listcontrol-element-format.md) Define um formato de lista para a exibição.

[Elemento ListEntry (Format)](./listentry-element-for-listcontrol-format.md) Fornece uma definição da exibição de lista.

[Elemento ListEntries (formato)](./listentries-element-for-listcontrol-format.md) Define como as linhas da exibição de lista são exibidas.

[Elemento ListItem (formato)](./listitem-element-for-listitems-for-listcontrol-format.md) Define a propriedade ou o script cujo valor é exibido em uma linha da exibição de lista.

[Elemento ListItems (formato)](./listitems-element-for-listentry-for-listcontrol-format.md) Define as propriedades e os scripts que são exibidos no modo de exibição de lista.

[Elemento Name para controle de controles para configuração (Format)](./name-element-for-control-for-controls-for-configuration-format.md) Especifica o nome do controle. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

[Elemento Name para SelectionSet (Format)](./name-element-for-selectionset-format.md) Especifica o nome usado para fazer referência ao conjunto de seleção.

[Elemento de nome para exibição (formato)](./name-element-for-view-format.md) Especifica o nome que é usado para identificar a exibição.

[Elemento de nova linha para CustomItem para controles para configuração (formato)](./newline-element-for-customitem-for-controls-for-configuration-format.md) Adiciona uma linha em branco à exibição do controle. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

[Elemento de nova linha para CustomItem para controles para View (Format)](./newline-element-for-customitem-for-controls-for-view-format.md) Adiciona uma linha em branco à exibição do controle. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

[Elemento de nova linha para CustomItem para CustomControl para exibição (formato)](./newline-element-for-customitem-for-customcontrol-for-view-format.md) Adiciona uma linha em branco à exibição do controle. Esse elemento é usado ao definir um modo de exibição de controle personalizado.

[Elemento de nova linha para CustomItem para GroupBy (Format)](./newline-element-for-customitem-for-groupby-format.md) Adiciona uma linha em branco à exibição do controle. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

[Elemento PropertyName para ExpressionBinding para controles para configuração (Format)](./propertyname-element-for-expressionbinding-for-controls-for-configuration-format.md) Especifica a propriedade .NET cujo valor é exibido pelo controle comum. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

[Elemento PropertyName para ExpressionBinding para controles para View (Format)](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md) Especifica a propriedade .NET cujo valor é exibido pelo controle. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

[Elemento PropertyName para ExpressionBinding para CustomControl para exibição (Format)](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md) Especifica a propriedade .NET cujo valor é exibido pelo controle. Este elemento é usado ao definir um modo de exibição de controle personalizado

[Elemento PropertyName para ExpressionBinding para GroupBy (Format)](./propertyname-element-for-expressionbinding-for-groupby-format.md) Especifica a propriedade .NET cujo valor é exibido pelo controle. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

[Elemento PropertyName para GroupBy (Format)](./propertyname-element-for-groupby-format.md) Especifica a propriedade .NET que inicia um novo grupo sempre que seu valor é alterado.

[Elemento PropertyName para ItemSeclectionCondition para controles para configuração (formato)](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) Especifica a propriedade .NET que dispara a condição. Quando essa propriedade está presente ou quando é avaliada como `true`, a condição é atendida e o controle é usado. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

[Elemento PropertyName para ItemSelectionCondition para controles para View (Format)](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md) Especifica a propriedade .NET que dispara a condição. Quando essa propriedade está presente ou quando é avaliada como `true`, a condição é atendida e o controle é usado. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

[Elemento PropertyName para ItemSelectionCondition para CustomControl para exibição (Format](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) especifica a propriedade .NET que dispara a condição. Quando essa propriedade está presente ou quando é avaliada como `true`, a condição é atendida e o controle é usado. Esse elemento é usado ao definir um modo de exibição de controle personalizado.

[Elemento PropertyName para ItemSelectionCondition para GroupBy (Format)](./propertyname-element-for-itemselectioncondition-for-groupby-format.md) Especifica a propriedade .NET que dispara a condição. Quando essa propriedade está presente ou quando é avaliada como `true`, a condição é atendida e o controle é usado. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

[Elemento PropertyName para ItemSelectionCondition para ListItem (Format)](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md) Especifica a propriedade .NET que dispara a condição. Quando essa propriedade está presente ou quando é avaliada como `true`, a condição é atendida e a exibição é usada. Esse elemento é usado ao definir um modo de exibição de lista.

[Elemento PropertyName para ListItem para ListControl (formato)](./propertyname-element-for-listitem-for-listcontrol-format.md) Especifica a propriedade .NET cujo valor é exibido na lista.

[Elemento PropertyName para SelectionCondition para EntrySelectedBy para ListEntry (Format)](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md) Especifica a propriedade .NET que dispara a condição. Quando essa propriedade está presente ou quando é avaliada como `true`, a condição é atendida e a entrada é usada. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

[Elemento PropertyName para SelectionCondition para controles para View (Format)](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md) Especifica a propriedade .NET que dispara a condição. Quando essa propriedade está presente ou quando é avaliada como `true`, a condição é atendida e a entrada é usada. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

[Elemento PropertyName para SelectionCondition para CustomControl para exibição (formato)](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md) Especifica a propriedade .NET que dispara a condição. Quando essa propriedade está presente ou quando é avaliada como `true`, a condição é atendida e a definição é usada. Esse elemento é usado ao definir um modo de exibição de controle personalizado.

[Elemento PropertyName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (Format)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md) Especifica a propriedade .NET que dispara a condição. Quando essa propriedade está presente ou quando é avaliada como `true`, a condição é atendida e a definição é usada.

[Elemento PropertyName para SelectionCondition para GroupBy (Format)](./propertyname-element-for-selectioncondition-for-groupby-format.md) Especifica a propriedade .NET que dispara a condição. Quando essa propriedade está presente ou quando é avaliada como `true`, a condição é atendida e a definição é usada. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

[Elemento PropertyName para SelectionCondition para EntrySelectedBy para ListEntry (Format)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md) Especifica a propriedade .NET que dispara a condição. Quando essa propriedade está presente ou quando é avaliada como `true`, a condição é atendida e a entrada da lista é usada.

[Elemento PropertyName para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md) Especifica a propriedade .NET que dispara a condição. Quando essa propriedade está presente ou quando é avaliada como `true`, a condição é atendida e a entrada da tabela é usada.

[Elemento PropertyName para SelectionCondition para EntrySelectedBy para WideEntry (Format)](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md) Especifica a propriedade .NET que dispara a condição. Quando essa propriedade está presente ou quando é avaliada como `true`, a condição é atendida e a definição é usada.

[Elemento PropertyName para TableColumnItem (Format)](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md) Especifica a propriedade cujo valor é exibido na coluna da linha.

[Elemento PropertyName para WideItem (Format)](./propertyname-element-for-wideitem-for-widecontrol-format.md) Especifica a propriedade do objeto cujo valor é exibido na exibição ampla.

[Elemento RightIndent para frame para controles para configuração (Format)](./rightindent-element-for-frame-for-controls-for-configuration-format.md) Especifica quantos caracteres os dados são deslocados para fora da margem direita. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

[Elemento RightIndent do quadro de controles de View (Format)](./rightindent-element-for-frame-for-controls-for-view-format.md) Especifica quantos caracteres os dados são deslocados para fora da margem direita. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

[Elemento RightIndent](./rightindent-element-for-frame-for-customcontrol-for-view-format.md) Especifica quantos caracteres os dados são deslocados para fora da margem direita. Esse elemento é usado ao definir um modo de exibição de controle personalizado.

[Elemento RightIndent para frame para GroupBy (Format)](./rightindent-element-for-frame-for-groupby-format.md) Especifica quantos caracteres os dados são deslocados para fora da margem direita. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

[Elemento ScriptBlock para ExpressionBinding para controles para configuração (Format)](./scriptblock-element-for-expressionbinding-for-controls-for-configuration-format.md) Especifica o script cujo valor é exibido pelo controle comum. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

[Elemento ScriptBlock para ExpressionBinding para controles para View (Format)](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md) Especifica o script cujo valor é exibido pelo controle. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

[Elemento ScriptBlock para ExpressionBinding para CustomCustomControl para View (Format)](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md) Especifica o script cujo valor é exibido pelo controle. Esse elemento é usado ao definir um modo de exibição de controle personalizado.

[Elemento ScriptBlock para ExpressionBinding para GroupBy (Format)](./scriptblock-element-for-expressionbinding-for-groupby-format.md) Especifica o script cujo valor é exibido pelo controle. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

[Elemento ScriptBlock para GroupBy (Format)](./scriptblock-element-for-groupby-format.md) Especifica o script que inicia um novo grupo sempre que seu valor é alterado.

[Elemento ScriptBlock para ItemSelectionCondition para controles para configuração (Format)](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) Especifica o script que dispara a condição. Quando esse script é avaliado como `true`, a condição é atendida e o controle é usado. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

[Elemento ScriptBlock para ItemSelectionCondition para controles para View (Format)](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md) Especifica o script que dispara a condição. Quando esse script é avaliado como `true`, a condição é atendida e o controle é usado. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

[Elemento ScriptBlock para ItemSelectionCondition para CustomControl para View (Format)](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) Especifica o script que dispara a condição. Quando esse script é avaliado como `true`, a condição é atendida e o controle é usado. Esse elemento é usado ao definir um modo de exibição de controle personalizado.

[Elemento ScriptBlock para ItemSelectionCondition para GroupBy (Format)](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md) Especifica o script que dispara a condição. Quando esse script é avaliado como `true`, a condição é atendida e o controle é usado. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

[Elemento ScriptBlock para ItemSelectionCondition para ListControl (Format)](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md) Especifica o script que dispara a condição. Quando esse script é avaliado como `true`, a condição é atendida e o item de lista é usado. Esse elemento é usado ao definir um modo de exibição de lista.

[Elemento ScriptBlock para ListItem (Format)](./scriptblock-element-for-listitem-for-listcontrol-format.md) Especifica o script cujo valor é exibido na linha da lista.

[Elemento ScriptBlock para SelectionCondition para controles para configuração (Format)](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md) Especifica o script que dispara a condição. Quando esse script é avaliado como `true`, a condição é atendida e a definição é usada. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

[Elemento ScriptBlock para SelectionCondition para controles para View (Format)](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md) Especifica o script que dispara a condição. Quando esse script é avaliado como `true`, a condição é atendida e a definição é usada. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

[Elemento ScriptBlock para SelectionCondition para CustomControl para View (Format)](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md) Especifica o script que dispara a condição. Quando esse script é avaliado como `true`, a condição é atendida e a definição é usada. Esse elemento é usado ao definir um modo de exibição de controle personalizado.

[Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para EnumerableExpansion (Format)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md) Especifica o script que dispara a condição.

[Elemento ScriptBlock para SelectionCondition para GroupBy (Format)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format.md) Especifica o script que dispara a condição. Quando esse script é avaliado como `true`, a condição é atendida e a definição é usada. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

[Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para ListEntry (Format)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md) Especifica o script que dispara a condição. Quando esse script é avaliado como `true`, a condição é atendida e a entrada da lista é usada.

[Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md) Especifica o bloco de script que dispara a condição. Quando esse script é avaliado como `true`, a condição é atendida e a entrada da tabela é usada.

[Elemento ScriptBlock para SelectionCondition para EntrySelectedBy para WideEntry (Format)](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md) Especifica o script que dispara a condição. Quando esse script é avaliado como `true`, a condição é atendida e a definição de entrada larga é usada.

[Elemento ScriptBlock para TableColumnItem (Format)](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md) Especifica o script cujo valor é exibido na coluna da linha.

[Elemento ScriptBlock para WideItem (Format)](./scriptblock-element-for-wideitem-for-widecontrol-format.md) Especifica o script cujo valor é exibido na exibição ampla.

[Elemento SelectionCondition para EntrySelectedBy para CustomEntry para configuração (formato)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md) Define uma condição que deve existir para que uma definição de controle comum seja usada. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

[Elemento SelectionCondition para EntrySelectedBy para controles para View (Format)](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md) Define uma condição que deve existir para que a definição de controle seja usada. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

[Elemento SelectionCondition para EntrySelectedBy para CustomControl para exibição (formato)](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md) Define uma condição que deve existir para que uma definição de controle seja usada. Esse elemento é usado ao definir um modo de exibição de controle personalizado.

[Elemento SelectionCondition para EntrySelectedBy para EnumerableExpansion (Format)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md) Define a condição que deve existir para expandir os objetos de coleção dessa definição.

[Elemento SelectionCondition para EntrySelectedBy para GroupBy (Format)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md) Define uma condição que deve existir para que uma definição de controle seja usada. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

[Elemento SelectionCondition para EntrySelectedBy para ListEntry (Format)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) Define a condição que deve existir para usar essa definição da exibição de lista. Não há nenhum limite para o número de condições de seleção que podem ser especificadas para uma definição de lista.

[Elemento SelectionCondition para EntrySelectedBy para TableRowEntry (Format)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md) Define a condição que deve existir para ser usada para esta definição da exibição de tabela. Não há nenhum limite para o número de condições de seleção que podem ser especificadas para uma definição de tabela.

[Elemento SelectionCondition para EntrySelectedBy para WideEntry (Format)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md) Define a condição que deve existir para que essa definição seja usada. Não há nenhum limite para o número de condições de seleção que podem ser especificadas para uma definição de entrada ampla.

[Elemento SelectionSet (formato)](./selectionset-element-format.md) Define um conjunto de objetos .NET que podem ser referenciados pelo nome do conjunto.

[Elemento SelectionSetName para EntrySelectedBy para controles para configuração (Format)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md) Especifica um conjunto de tipos .NET que usam essa definição do controle. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

[Elemento SelectionSetName para EntrySelectedBy para controles para View (Format)](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md) Especifica um conjunto de tipos .NET que usam essa definição do controle. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

[Elemento SelectionSetName para EntrySelectedBy para CustomEntry (Format)](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md) Especifica um conjunto de objetos .NET para a entrada de lista. Não há nenhum limite para o número de conjuntos de seleção que podem ser especificados para uma entrada.

[Elemento SelectionSetName para EntrySelectedBy para EnumerableExpansion (Format)](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md) Especifica o conjunto de tipos .NET que são expandidos por essa definição.

[Elemento SelectionSetName para EntrySelectedBy para GroupBy (Format)](./selectionsetname-element-for-entryselectedby-for-groupby-format.md) Especifica um conjunto de objetos .NET para a entrada de lista. Não há nenhum limite para o número de conjuntos de seleção que podem ser especificados para uma entrada. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

[Elemento SelectionSetName para EntrySelectedBy para ListEntry (Format)](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) Especifica um conjunto de objetos .NET para a entrada de lista. Não há nenhum limite para o número de conjuntos de seleção que podem ser especificados para uma entrada.

[Elemento SelectionSetName para EntrySelectedBy para TableRowEntry (Format)](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md) Especifica um conjunto de tipos .NET que usam esta entrada da exibição de tabela. Não há nenhum limite para o número de conjuntos de seleção que podem ser especificados para uma entrada.

[Elemento SelectionSetName para EntrySelectedBy para WideEntry (Format)](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md) Especifica um conjunto de objetos .NET para a definição. A definição é usada sempre que um desses objetos é exibido.

[Elemento SelectionSetName para SelectionCondition para controles para configuração (Format)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md) Especifica o conjunto de tipos .NET que disparam a condição. Quando qualquer um dos tipos nesse conjunto estiver presente, a condição será atendida e o objeto será exibido usando esse controle. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

[Elemento SelectionSetName para SelectionCondition para controles para View (Format)](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md) Especifica o conjunto de tipos .NET que disparam a condição. Quando qualquer um dos tipos nesse conjunto estiver presente, a condição será atendida e o objeto será exibido usando esse controle. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

[Elemento EntrySelectedBy para CustomEntry para exibição (formato)](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md) Especifica o conjunto de tipos .NET que disparam a condição. Quando qualquer um dos tipos nesse conjunto estiver presente, a condição será atendida e o objeto será exibido usando esse controle. Esse elemento é usado ao definir um modo de exibição de controle personalizado.

[Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (Format)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md) Especifica o conjunto de tipos .NET que disparam a condição. Quando qualquer um dos tipos nesse conjunto estiver presente, a condição será atendida.

[Elemento SelectionSetName para SelectionCondition para GroupBy (Format)](./selectionsetname-element-for-selectioncondition-for-groupby-format.md) Especifica o conjunto de tipos .NET que disparam a condição. Quando qualquer um dos tipos nesse conjunto estiver presente, a condição será atendida e o objeto será exibido usando esse controle. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

[Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para ListEntry (Format)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md) Especifica o conjunto de tipos .NET que disparam a condição. Quando qualquer um dos tipos nesse conjunto estiver presente, a condição será atendida e o objeto será exibido usando essa definição da exibição de lista.

[Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md) Especifica o conjunto de tipos .NET que disparam a condição. Quando qualquer um dos tipos nesse conjunto estiver presente, a condição será atendida e o objeto será exibido usando essa definição da exibição de tabela.

[Elemento SelectionSetName para SelectionCondition para EntrySelectedBy para WideEntry (Format)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md) Especifica o conjunto de tipos .NET que disparam a condição. Quando qualquer um dos tipos nesse conjunto estiver presente, a condição será atendida e o objeto será exibido usando essa definição da exibição ampla.

[Elemento SelectionSetName para ViewSelectedBy (Format)](./selectionsetname-element-for-viewselectedby-format.md) Especifica um conjunto de objetos .NET que são exibidos pela exibição.

[Elemento SelectionSets (Format)](./selectionsets-element-format.md) Define os conjuntos de objetos .NET que podem ser usados por exibições de formato individuais.

[Elemento TextError (formato)](./showerror-element-format.md) Especifica que o registro de erro completo é exibido quando ocorre um erro durante a exibição de um dado.

[Elemento TableColumnHeader para TableHeaders para TableControl (Format)](./tablecolumnheader-element-format.md) Define o rótulo, a largura da coluna e o alinhamento do rótulo para uma coluna da tabela.

[Elemento TableColumnItem (Format)](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) Define a propriedade ou o script cujo valor é exibido na coluna da linha.

[Elemento TableColumnItems (Format)](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md) Define as propriedades ou os scripts cujos valores são exibidos na linha.

[Elemento TableControl (Format)](./tablecontrol-element-format.md) Define um formato de tabela para uma exibição.

[Elemento TableHeaders (Format)](./tableheaders-element-format.md) Define os cabeçalhos para as colunas de uma tabela.

[Elemento TableRowEntries (Format)](./tablerowentries-element-for-tablecontrol-format.md) Define as linhas da tabela.

[Elemento TableRowEntry (Format)](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md) Define os dados que são exibidos em uma linha da tabela.

[Elemento Text para CustomItem para controles para configuração (Format)](./text-element-for-customitem-for-controls-for-configuration-format.md) Especifica o texto que é adicionado aos dados que são exibidos pelo controle, como um rótulo, colchetes para colocar os dados e espaços para recuar os dados. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

[Elemento Text para CustomItem para controles para View (Format)](./text-element-for-customitem-for-controls-for-view-format.md) Especifica o texto que é adicionado aos dados que são exibidos pelo controle, como um rótulo, colchetes para colocar os dados e espaços para recuar os dados. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

[Elemento Text para CustomItem (Format)](./text-element-for-customitem-for-customview-for-view-format.md) Especifica o texto que é adicionado aos dados que são exibidos pelo controle, como um rótulo, colchetes para colocar os dados e espaços para recuar os dados. Esse elemento é usado ao definir um modo de exibição de controle personalizado.

[Elemento Text para CustomItem para GroupBy (Format)](./text-element-for-customitem-for-groupby-format.md) Especifica o texto que é adicionado aos dados que são exibidos pelo controle, como um rótulo, colchetes para colocar os dados e espaços para recuar os dados. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

[Elemento TypeName para EntrySelectedBy para controles para configuração (Format)](./typename-element-for-entryselectedby-for-controls-for-configuration-format.md) Especifica um tipo .NET que usa essa definição do controle. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

[Elemento TypeName para EntrySelectedBy para controles para View (Format)](./typename-element-for-entryselectedby-for-controls-for-view-format.md) Especifica um tipo .NET que usa essa definição do controle. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

[Elemento TypeName para EntrySelectedBy para CustomEntry para exibição (formato)](./typename-element-for-entryselectedby-for-customentry-for-view-format.md) Especifica um tipo .NET que usa essa definição do modo de exibição de controle personalizado. Não há nenhum limite para o número de tipos que podem ser especificados para uma definição.

[Elemento TypeName para EntrySelectedBy para EnumerableExpansion (Format)](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md) Especifica um tipo .NET que é expandido por essa definição. Esse elemento é usado ao definir as configurações padrão.

[Elemento TypeName para EntrySelectedBy para GroupBy (Format)](./typename-element-for-entryselectedby-for-groupby-format.md) Especifica um tipo .NET que usa essa definição do controle personalizado. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

[Elemento TypeName para EntrySelectedBy para ListControl (Format)](./typename-element-for-entryselectedby-for-listcontrol-format.md) Especifica um tipo .NET que usa essa entrada da exibição de lista. Não há nenhum limite para o número de tipos que podem ser especificados para uma entrada de lista.

[Elemento TypeName para EntrySelectedBy para TableRowEntry (Format)](./typename-element-for-entryselectedby-for-tablecontrol-format.md) Especifica um tipo .NET que usa essa entrada da exibição de tabela. Não há nenhum limite para o número de tipos que podem ser especificados para uma entrada de tabela.

[Elemento TypeName para EntrySelectedBy para WideEntry (Format)](./typename-element-for-entryselectedby-for-wideentry-format.md) Especifica um tipo .NET para a definição. A definição é usada sempre que este objeto é exibido.

[Elemento TypeName para SelectionCondition para controles para configuração (Format)](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md) Especifica um tipo .NET que dispara a condição. Esse elemento é usado ao definir um controle comum que pode ser usado por todas as exibições no arquivo de formatação.

[Elemento TypeName para SelectionCondition para controles para View (Format)](./typename-element-for-selectioncondition-for-controls-for-view-format.md) Especifica um tipo .NET que dispara a condição. Esse elemento é usado ao definir controles que podem ser usados por uma exibição.

[Elemento TypeName para SelectionCondition para CustomControl para exibição (formato)](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md) Especifica um tipo .NET que dispara a condição. Esse elemento é usado ao definir um modo de exibição de controle personalizado.

[Elemento TypeName para SelectionCondition para EntrySelectedBy para EnumerableExpansion (Format)](./typename-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md) Especifica um tipo .NET que dispara a condição.

[Elemento TypeName para SelectionCondition para GroupBy (Format)](./typename-element-for-selectioncondition-for-groupby-format.md) Especifica um tipo .NET que dispara a condição. Esse elemento é usado ao definir como um novo grupo de objetos é exibido.

[Elemento TypeName para SelectionCondition para EntrySelectedBy para ListControl (Format)](./typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md) Especifica um tipo .NET que dispara a condição. Quando esse tipo está presente, a entrada da lista é usada.

[Elemento TypeName para SelectionCondition para EntrySelectedBy para TableRowEntry (Format)](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md) Especifica um tipo .NET que dispara a condição. Quando esse tipo está presente, a condição é atendida e a linha da tabela é usada.

[Elemento TypeName para SelectionCondition para EntrySelectedBy para WideEntry (Format)](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md) Especifica um tipo .NET que dispara a condição. Quando esse tipo está presente, a definição é usada.

[Elemento TypeName para tipos (Format)](./typename-element-for-types-format.md) Especifica o tipo .NET de um objeto que pertence ao conjunto de seleção.

[Elemento TypeName para ViewSelectedBy (Format)](./typename-element-for-viewselectedby-format.md) Especifica um objeto .NET que é exibido pela exibição.

[Elemento Types (formato)](./types-element-for-selectionset-format.md) Define os objetos .NET que estão no conjunto de seleção.

[Elemento View (formato)](./view-element-format.md) Define uma exibição usada para exibir um ou mais objetos .NET.

[Elemento ViewDefinitions (Format)](./viewdefinitions-element-format.md) Define as exibições usadas para exibir objetos.

[Elemento ViewSelectedBy (Format)](./viewselectedby-element-format.md) Define os objetos .NET que são exibidos pela exibição.

[Elemento WideControl (Format)](./widecontrol-element-format.md) Define um formato de lista largo (valor único) para a exibição. Essa exibição mostra um valor de propriedade única ou um valor de script para cada objeto.

[Elemento WideEntries (Format)](./wideentries-element-for-widecontrol-format.md) Fornece as definições da exibição ampla. A exibição ampla deve especificar uma ou mais definições.

[Elemento WideEntry (Format)](./wideentry-element-for-widecontrol-format.md) Fornece uma definição da exibição ampla.

[Elemento WideItem (Format)](./wideitem-element-for-widecontrol-format.md) Define a propriedade ou o script cujo valor é exibido.

[Elemento Width (Format)](./width-element-for-tablecolumnheader-for-tablecontrol-format.md) Define a largura (em caracteres) de uma coluna.

[Elemento Wrap (Format)](./wrap-element-for-tablerowentry-for-tablecontrol-format.md) Especifica que o texto que excede a largura da coluna é exibido na próxima linha.

[Elemento WrapTables (Format)](./wraptables-element-format.md) Especifica que os dados em uma célula de tabela serão movidos para a próxima linha se os dados forem maiores do que a largura da coluna.

## <a name="see-also"></a>Consulte Também

[Gravando um arquivo de formatação do PowerShell](./writing-a-powershell-formatting-file.md)
